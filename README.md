# E-commerce Design Assignment

## High Level Design

![activity-diagram](assets/activity-diagram.png)

The diagram depicted above provides a simple perspective of a basic e-commerce system using an activity diagram. It illustrates the procedure of displaying detail product to the user and create an order for the chosen product.

## Create Order Details

The image presented below provides a summary of the order flow, on the assumption that user information and product specifics are present in the database.

![sequence-diagram](assets/sequence-diagram.png)

The following is an in-depth pseudocode process for create an order.:

```pseudocode
// Get the product by ID, check if the product is in stock

function createOrder(productID, quantity) {
  let totalprice = 0;
  for (productID in database) {
    let product = database.getProductById(productID);

    if (product.stock >= quantity) {
    product.stock -= quantity;
    totalprice += product.price * quantity;
    database.updateProductById(productID, product);
    order.push({
      "name": product.name,
      "quantity": quantity,
      "price": product.price,
    });
    }

    else {Print("Product out of stock.");
    }
  
  return {
    "totalPrice": totalPrice,
    "order": order
  };
}
```
## Complexity Analysis
The  complexity of this function is O(n), where n is the number of products in the database. This is because the function iterates over the database using a for loop, and performs a constant number of operations (i.e., accessing and updating the database, computing the total price, and creating a new order) for each product in the list.