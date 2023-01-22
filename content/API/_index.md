# Build a storefront using the Zid API

Zid's API contains all the elements necessary to build your own storefront. This tutorial will get you started on using the relevant API requests and teach you how to apply each request in context. 

### What you'll learn
By completing this tutorial, you will have accomplished the following:
- Generated an API access token for the Zid API. 
- Retrieved a list of products from your store together with each product's images. 

### Requirements
- You are a Zid partner.
- You have an existing web store integrated with Zid.
- You have a general understanding of REST APIs.

## Step-by-step guide

Here is a summary of the steps covered in this tutorial. 
- [Step 1: Generate an API access token](#step-1-generate-an-api-access-token). 
- [Step 2: Make an API request to fetch products](#step-2-make-an-api-request-to-fetch-products)
- [Step 3: Make an API request to fetch product images](#step-3-make-an-api-request-to-fetch-product-images)

{{% notice note %}}
The code examples used in this tutorial are in Javascript. For code examples in other languages and for more detail on the API requests used, refer to the [API documentation page](https://docs.zid.sa/docs/zid-merchant-api/o9kp944zroiq4-about-merchant-api).
{{% /notice %}}

### Quick Reference
This page uses the following functions from our API:
- [Get All products](https://docs.zid.sa/docs/zid-merchant-api/bb63d965c592c-get-all-products)
- [Get List of images of a product](https://docs.zid.sa/docs/zid-merchant-api/e35f7478acf6f-get-list-of-images-of-a-product).


### Step 1: Generate an API access token

1. Log in to your Zid merchant account. 
1. Navigate to your store's page. If you own more than one store, you can pick any one of them for the purpose of this tutorial. 
1. In the *Store information* section, Copy the value of `Store-id`. You will use this value in your API requests in the coming steps.
1. On the left-side menu, click **Settings**. 
1. Scroll down to the *API* section and click **Request API access token**.
   If you have already done this step, then you can use the API access token you created previously.
1. Copy the values for `Authorization` and `X-Manager-Token`. You will use these values in your API requests in the coming steps. Be sure to keep these values secret. 

### Step 2: Make an API request to fetch products

Now that you have an API access token, you can make requests to the Zid API.

Let's start by making a fetch request to retrieve the list of products in a store. 

```javascript
// Fill in the three values you copied from Step 1
const options = {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
    'Accept-Language': 'ar',
    ROLE: 'Manager',
    Authorization: '<YOUR AUTHORIZATION TOKEN>',
    'STORE-ID': '<YOUR STORE-ID>',
    'X-MANAGER-TOKEN': '<YOUR X-MANAGER-TOKEN>'
  }
};

// Fetch all products from your store
fetch('https://api.zid.sa/v1/products/', options).then((products) => {
  // Do something with the products
  console.log(products);
});
```

### Step 3: Make an API request to fetch product images

Now that we have retrieved all the products on our store, let's retrieve the images of a single product. In the following example, we fetch a single product by its ID along with the images of that product.

```javascript
// Fill in the three values you copied from Step 1
const options = {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
    'Accept-Language': 'ar',
    ROLE: 'Manager',
    Authorization: '<YOUR AUTHORIZATION TOKEN>',
    'STORE-ID': '<YOUR STORE-ID>',
    'X-MANAGER-TOKEN': '<YOUR X-MANAGER-TOKEN>'
  }
};


// Fetch a product by its ID along with its images. Fill in the product ID in place of <YOUR PRODUCT ID>
fetch('https://api.zid.sa/v1/products/<YOUR PRODUCT ID>/images/', options).then((images) => {
  // Do something with the product's images
  console.log(images);
});
```



## Next steps
Explore more of what you can achieve with Zid.
- [Manage a cart]() with the Zid API.
- [Create and complete a checkout]() with the Zid API.
- Learn how you can create a unique buying experience through apps in the [Zid App Marketplace](). 