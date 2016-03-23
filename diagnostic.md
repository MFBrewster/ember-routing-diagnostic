# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    In a router, you define URL paths. A route retrieves data to be handled by
    templates and cpmponents
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember g route compus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{link-to 'compus.boston'}}Boston Campus{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    The first route definition is nested, so all references to it must reference
    its parent path, and content from the child route will be displayed simul-
    taneously with content from the parent route.

    The second defintion is not nested, so it can be referenced without reference
    to its parent, and it will not be displayed simultaneously with the parent
    route's data
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    {{#each model as |foo|}} foo.bar {{/each}}
    ```
