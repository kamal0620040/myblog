---
title: Demystifying RESTful API
date: "2022-06-15T12:40:32.169Z"
template: "post"
draft: false
slug: "restfulapi"
category: "Web"
tags:
  - "Web"
  - "API"
description: "A blog about restful api."
socialImage: "/media/api.jpg"
---

- [API](#api)
- [But what makes the API restful?](#but-what-makes-the-api-restful)
- [Important three](#important-three)
- [Resources](#resources)
- [Resource Representation](#resource-representation)
- [HTTP Methods](#http-methods)

## API

When we need to expose our data to the client, like a web app running inside a browser or a mobile app running on a mobile device. So, this is where API comes into the picture. Building an API is essentially creating an interface that the client app uses to build and save data.  It's like building a remote control with a bunch of buttons where each button provides certain functionality. 

Similarly, our API is going to have endpoints for different purposes. If we consider an e-commerce site as an example, we can have endpoints for getting a list of products and creating, deleting, and updating them. We can have other endpoints for managing our shopping cart, orders, and soon.  

![apiendpoint.jpg](/media/endpoint.jpg)

The client app sends a request to these endpoints to get receive products, orders, shopping carts, and soon.

![request.jpg](/media/request.jpg)
![response.jpg](/media/response.jpg)

## But what makes the API restful?
![restful.jpg](/media/restful.jpg)

In practical term, REST define a bunch of rule for client and server to communicate over the web. Following those rules will help us build the system that is:
- Fast
- Scalable
- Reliable
- Easy to understand
- Easy to change

So, an API that conforms to these rules is called a restful API. 

## Important three
Three concepts that everyone should know about restful are:
- Resources
- Representations
- HTTP Methods


## Resources
The first key concept that we need to learn on RESTful API is the concept of resources. A resource in a restful API is like an object of your application like the product, collection, cart, etc in the case of ecommerce application. 

These resources are available on the web and client applications can access them using the URL.It's a way to locate a resource on the web. It's basically a web address. So assuming the  site is hosted at http://example.com we can access all products by 
http://example.com/products

If we want to access the individual resources like an individual product we append its id to the URL.
http://example.com/products/1

Now, a resource may contain another resource. For example, a given product can have one or more than one reviews. So, using the following URL we can get all the reviews for product number 1.
http://example.com/products/1/reviews

Or, if we want to get the first review of the first product. we can get it by:
http://example.com/products/1/reviews/1

So, in the above, we can see the pattern between all the URLs so if we follow this pattern our API will be familiar for others to understand.

## Resource Representation
So, we can identify resources using its URL. Now if we hit that URL server is going to return the resource in a certain format or representation. It may return as :
- HTML
- XML (old format)
- JSON (modern - currently most app use)

What is important here is none of these are the internal representation of the resources of the server. In other words, on the server, we identify a resource like a product using an object or an instance of the python class(🐍).

![pythonclass.jpg](/media/pythonclass.jpg)

But when we return these objects to the client we represent them in HTML, XML, or JSON. Because these are the format that clients understand. 

> REST does not dictate the representation format that we should use. So it is completely up to us which format we want to use.

![json.jpg](/media/json.jpg)

It's the notation we used to represent objects in JavaScript.  Here is the example of the product represented using the JSON:

    {
        "name": "kamal",
        "age": 19,
        "is-online": true,
        "interest": []
    }

## HTTP Methods
So, when building the restful API we expose one or more endpoints to the client.  Each endpoint supports various kinds of operation. Some endpoints may allow only accessing data while others may allow to modify or delete data. This is where the HTTP method comes into the picture.

Using the HTTP method the client can tell the server what it wants to do with the resources. So, HTTP defines the methods like:
- GET - for getting the resource or collection of resources 
- POST - for creating the resource
- PUT - for updating it
- PATCH - for updating part of it like the subset of property 
- DELETE - for deleting the resources

So, now lets go through the few scenarios. Let's say we want to create a product.
In our client app, we send the post request to the product endpoint so the server knows we want to create the product.
>But where is the product we want to create? 

We are going to insert it as a JSON object into the body of the request. So, the server will read this product and create it.

![post-product.jpg](/media/post-product.jpg)

Now, let's say we want to update product number 1:

First, we need to figure out are we going to update all properties or only a subset of the property of product 1. If we want to update all the property we should send the PUT request otherwise we should send the PATCH request to the URL.

![patch-product.jpg](/media/patch-product.jpg)

Now to delete the product we send the delete request to the server. 

In this case, nothing is included in the body because all the server needs to delete the product is its id which is included in the URL.