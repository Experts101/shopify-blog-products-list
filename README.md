# Shopify blog products list
How to show dynamic list of product within the blog post content in Shopify.


# Embedding Product List in Blog Post
This guide demonstrates how to insert a product list into a blog post article using a Liquid template. This feature allows you to seamlessly integrate product displays within your Shopify blog content.

# Description
The provided code splits the blog article content to dynamically inject products between sections of text using custom delimiters [PROD] and [/PROD]. This functionality is ideal for highlighting products within informative articles or promotional posts.

# Setup Instructions
Identify Blog Content: Ensure your blog post content includes product placeholders marked by the delimiters [PROD] and [/PROD].

# Code Implementation:
Embed the following Liquid template code in your Shopify theme to enable product listing in the blog-artical-content-products.liquid

# Customize Components:

Modify the slider-component class and settings to fit your design preferences.
Adjust slider attributes to match your layout and desired interactivity.
Usage:

Insert [PROD] within your blog content, followed by the product handles you wish to display, separated by commas (e.g., product1,product2). Close the list with [/PROD].
Example:
Here is some introductory content.
[PROD]product1,product2[/PROD]
Continuation of article after product list.

# Notes
Ensure product handles used within [PROD] are valid and exist in your store to avoid errors in rendering the template.
Customize styles and add functionalities, such as responsive behavior and accessibility improvements, as required for your store's design.
Ready to boost your article engagement with embedded product features? Implement this template and transform your blog into an interactive shopping platform!

# Only for dawn theme user

We need to add below files at the top of the main-article.liquid to correctly work product card.

{{ 'section-blog-post.css' | asset_url | stylesheet_tag }}
{{ 'component-card.css' | asset_url | stylesheet_tag }}
{{ 'component-price.css' | asset_url | stylesheet_tag }}

{{ 'component-slider.css' | asset_url | stylesheet_tag }}

{%- unless section.settings.quick_add == 'none' -%}
  {{ 'quick-add.css' | asset_url | stylesheet_tag }}
  <script src="{{ 'product-form.js' | asset_url }}" defer="defer"></script>
{%- endunless -%}

{%- if section.settings.quick_add == 'standard' -%}
  <script src="{{ 'quick-add.js' | asset_url }}" defer="defer"></script>
{%- endif -%}

{%- if section.settings.quick_add == 'bulk' -%}
  <script src="{{ 'quick-add-bulk.js' | asset_url }}" defer="defer"></script>
  <script src="{{ 'quantity-popover.js' | asset_url }}" defer="defer"></script>
  <script src="{{ 'price-per-item.js' | asset_url }}" defer="defer"></script>
  <script src="{{ 'quick-order-list.js' | asset_url }}" defer="defer"></script>
{%- endif -%}
