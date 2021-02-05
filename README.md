[![Codacy Badge](https://api.codacy.com/project/badge/Grade/1835e693354349ffaa703c0bbaf2b52b)](https://app.codacy.com/gh/w3bdesign/nuxtjs-woocommerce?utm_source=github.com&utm_medium=referral&utm_content=w3bdesign/nuxtjs-woocommerce&utm_campaign=Badge_Grade)
[![CodeFactor](https://www.codefactor.io/repository/github/w3bdesign/nuxtjs-woocommerce/badge)](https://www.codefactor.io/repository/github/w3bdesign/nuxtjs-woocommerce)
[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=w3bdesign_nuxtjs-woocommerce&metric=alert_status)](https://sonarcloud.io/dashboard?id=w3bdesign_nuxtjs-woocommerce)
[![Code Smells](https://sonarcloud.io/api/project_badges/measure?project=w3bdesign_nuxtjs-woocommerce&metric=code_smells)](https://sonarcloud.io/dashboard?id=w3bdesign_nuxtjs-woocommerce)
[![Technical Debt](https://sonarcloud.io/api/project_badges/measure?project=w3bdesign_nuxtjs-woocommerce&metric=sqale_index)](https://sonarcloud.io/dashboard?id=w3bdesign_nuxtjs-woocommerce)

# NuxtJS Ecommerce site with WooCommerce backend

<img src="https://user-images.githubusercontent.com/45217974/106988377-f129a080-676f-11eb-94b9-a44c86ea6c79.png" alt="Project screenshot" />

## This is currently a work in progress!

## Table Of Contents (TOC)

-   [Installation](#Installation)
-   [Features](#Features)
-   [Troubleshooting](#Troubleshooting)
-   [TODO](#TODO)

## Installation

1.  Install and activate the following required plugins, in your WordPress plugin directory:

-   [woocommerce](https://wordpress.org/plugins/woocommerce) Ecommerce for WordPress.
-   [wp-graphql](https://wordpress.org/plugins/wp-graphql) Exposes GraphQL for WordPress.
-   [wp-graphql-woocommerce](https://github.com/wp-graphql/wp-graphql-woocommerce) Adds WooCommerce functionality to a WPGraphQL schema.
-   [algolia-woo-indexer](https://github.com/w3bdesign/algolia-woo-indexer) Sends WooCommerce products to Algolia. Required for search to work.
-   [wp-graphql-cors](https://github.com/funkhaus/wp-graphql-cors) Ensures that CORS works correctly. Remember to add the domain to the store under `Extend "Access-Control-Allow-Origin” header`

Optional plugin:

-   [headless-wordpress](https://github.com/w3bdesign/headless-wp) Disables the frontend so only the backend is accessible. (optional)

The current release has been tested and is confirmed working with the following versions:

-   WordPress version 5.6.0
-   WooCommerce version 4.9.0
-   WP GraphQL version 1.1.2
-   WooGraphQL version 0.6.1 (latest development version)
-   WPGraphQL CORS version 1.1.0 (with introspection enabled)

2.  For debugging and testing, install either:

    <https://addons.mozilla.org/en-US/firefox/addon/apollo-developer-tools/> (Firefox)

    <https://chrome.google.com/webstore/detail/apollo-client-developer-t/jdkknkkbebbapilgoeccciglkfbmbnfm> (Chrome)

    Rename .env.example to .env so the Apollo debugger will correctly load. It will not load if the NODE_ENV variable is not correctly set.

3.  Make sure WooCommerce has some products already or import some sample products

    The WooCommerce sample products CSV file is available at `wp-content/plugins/woocommerce/sample-data/sample_products.csv` or [Sample products](sample_products/)

    Import the products at `WP Dashboard > Tools > Import > WooCommerce products(CSV)`

4.  Clone or fork the repo and modify `.env` with the URL to the GraphQL endpoint (or set environment variables in the configuration UI for your deployment solution)

5.  Start the server with `npm run dev`

6.  Enable COD (Cash On Demand) payment method in WooCommerce

7.  Add a product to the cart

8.  Proceed to checkout

9.  Fill in your details and place the order

## Features

-   NuxtJS
-   Tailwind CSS
-   Vue Apollo with GraphQL Codegen
-   Vue Awesome Swiper for image slider on frontpage
-   Responsive design
-   Support for simple products
-   GraphQL-based filters
-   CSS animations and transitions
-   Form handling and validation with Vue Formulate
-   Checkout process
-   Animated mobile menu

## Troubleshooting

**I am getting a cart undefined error?**

Check that you are using the 0.6.1 version of the WooGraphQL plugin

**The products page isn't loading?**

Check the attributes of the products. Right now the application requires Size and Color.

## TODO

-   Look into variable product support
-   Make WooCommerce session token expire and get deleted after 24 hours
-   Finish implementing Algolia search
-   Make Algolia look good on mobile
