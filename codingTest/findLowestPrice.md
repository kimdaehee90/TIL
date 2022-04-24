## QUESTION DESCRIPTION
An e-commerce company is currently celebrating ten years in business. They are having a sale to honor their privileged members, those who have been using their services for the past five years. They receive the best discounts indicated by any discount tags attached to the product. Determine the minimum cost to purchase all products listed. As each potential price is calculated, round it to the nearest integer before adding it to the total. Return the cost to purchase all items as an integer.

### There are three types of discount tags :
- Type 0: discounted price, the item is sold for a given price.
- Type 1: percentage discount, the customer is given a fixed percentage discount from the retail price.
- Type 2: fixed discount, the customer is given a fixed amount off from the retail price.

### Example
products = [['10', 'd0', 'd1'] , ['15', 'EMPTY', 'EMPTY'] , ['20', 'd1', 'EMPTY']]
discounts = [['d0','1','27'], ['d1', '2', '5']]

The products array elements are in the form ['price', 'tag 1', 'tag 2', ..., 'tag m-1'].
There may be zero or more discount codes associated with a product.
Discount tags in the products array may be 'EMPTY' which is the same as a null value.
The discounts array elements are in the form ['tag', 'type', 'amount'].
If a privileged member buys product 1 listed at a price of 10 with two discounts available:
Under discount d0 of type 1, the discounted price is 10 - 10 * 0.27 = 7.30, round to 7.
Under discount d1 of type 2, the discounted price is 10 - 5 = 5.
The price to purchase the product 1 is the lowest of the two, or 5 in this case
The second product is priced at 15 because there are no discounts available
The third product is priced at 20. Using discount tag d1 of type 2, the discounted price is 20-5 = 15

The total price to purchase the three items is 5 + 15 + 15 = 35

Notes: Not all items will have the maximum number of tags. Empty tags may just not exist in input, or they may be filled with the string EMPTY. These are equivalent as demonstrated in the example above.

### Function Description 
Complete the function findLowestPrice in the editor below.
findLowestPrice has the following parameter(s):
[string] products[n][m]: a 2D array of product descriptors as strings: price followed by up to m-1 discount tags [string] discounts[d][3]: a 2D array of tag descriptors as strings: tag, type, amount Returns: int: the total amount paid for all listed products, discounted to privileged members' pricing.

Constraints
1 ≤ n, m, d ≤ 1000

- Input Format For Custom Testing
The first line contains an integer, n, the size of the array products.
The next line contains an integer, m, the number of elements in each products[i].
Each line i of the n subsequent lines (where 0 ≤ i < n) contains an array of strings describing the product.
details: price followed by applicable discount tags, or EMPTY.

QUESTION DESCRIPTION Correct Answer Score 7 3/13
The next line contains an integer, d, the size of the array discounts.
The next line contains an integer, 3, denoting the count of the attributes of each discount.
Each line j of the d subsequent lines (where 0 ≤ j < d) contains an array of strings describing the discount details.

- Sample Case 0
  Sample Input 0

STDIN	Function
------	-------- 
2  		→ products[] size n = 2
3 		→ products[i] size m = 3
10 sale january-sale → products = [['10', 'sale', 'january-sale'], ['200', 'sale', 'EMPTY']]
200 sale EMPTY
2		→ discounts[] size d = 2
3 		→ discounts[j] size = 3 (always)
sale 0 10 	→ discounts = [['sale', '0', '10'], ['january-sale', '1', '10']]
january-sale 1 10

Sample Output 0
19

Explanation 0
products = [['10', 'sale', 'january-sale'], ['200', 'sale', 'EMPTY']]
discounts = [['sale', '0', '10'], ['january-sale', '1', '10']]

If a privileged member buys product 1 listed at a price of 10 with two discounts available:
Under discount 'sale' of type 0, the item is sold for a given price 10
Under discount 'january-sale' of type 1, the discounted price is 10 - 0.1*10 = 9
The price to purchase the product 1 is the lowest of the two, or 9 in this case
The second product is priced at 200. Using 'sale' of type 0, the item is sold for a given price 10
The total price to purchase the three items is 9+10 = 19

***
## 내 풀이
~~~java
public static void main(String[] args) {
SpringApplication.run(DemoApplication.class, args);
System.out.println("hello world");
String[][] product = {{"10","d0","d1"},{"15","EMPTY","EMPTY"},{"20","d1","EMPTY"}};
String[][] discount = {{"d0","1","27"},{"d1","2","5"}};

		System.out.println(totalPrince(product, discount));
	}

	private static int totalPrince(String[][] products, String[][] discounts) {
		HashMap<String,Discount> dic = new HashMap<String, Discount>();
		for (String[] discount : discounts){
			int type = Integer.parseInt(discount[1]);
			int value = Integer.parseInt(discount[2]);
			dic.put(discount[0],new Discount(discount[0],type,value));
		}
		int res = 0;
		for (String[] product : products){
			int price = Integer.parseInt(product[0]);
			int min = price;
			for (int i = 1;i<product.length;i++){
				int curprice = price;
				String index = product[i];
				if(!index.equals("EMPTY")){
					Discount dis = dic.get(index);
					if(dis.type==0){
						curprice = dis.value;
					}
					else if (dis.type==1){
						curprice = curprice*(1-dis.value/100);
					}
					else if (dis.type==2){
						curprice-=dis.value;
					}
					min=Math.min(min, curprice);
				}
			}
			res+=min;
		}
		return res;
	}

	private static class Discount {
		String index;
		int type;
		int value;

		Discount(String index, int type, int value){
			this.index = index;
			this.type = type;
			this.value = value;
		}
	}
~~~