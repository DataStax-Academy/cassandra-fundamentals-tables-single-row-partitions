<!-- TOP -->
<div class="top">
  <img src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-logo.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Shopping Cart Data Modeling</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:aleksandr.volochnev@datastax.com">email</a> or <a href="https://dtsx.io/aleks">LinkedIn</a>.</span>
  </div>
</div>

<!-- NAVIGATION -->
<div id="navigation-top" class="navigation-top">
 <a href='command:katapod.loadPage?[{"step":"intro"}]' 
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 1 of 10</span>
 <a href='command:katapod.loadPage?[{"step":"step2-astra"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Connect to Astra DB and create a database</div>

✅ Create an application token to access Astra. Skip this step is you already have a token.

<ul>
  <li>Sign in (or sign up) to your Astra account at <a href="https://astra.datastax.com" target="_blank">astra.datastax.com</a></li>
  <li>Create an application token by following <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/" target="_blank">these instructions</a></li>
</ul>

You can reuse the same token in our other scenarios, too.

✅ Setup Astra CLI by providing your application token:
```
astra setup
```

✅ List your existing Astra DB databases:
```
astra db list
```

✅ Create database `data-modeling` and keyspace `shopping_cart_data` if they do not exist:
```
astra db create data-modeling -k shopping_cart_data --if-not-exist --wait
```

This operation may take a bit longer when creating a new database or resuming an existing hibernated database.

✅ Verify that database `data-modeling` is `ACTIVE` and keyspace `shopping_cart_data` exists:
```
astra db get data-modeling
```

✅ Start the CQL shell and connect to database `data-modeling` and keyspace `shopping_cart_data`:
```
clear
astra db cqlsh data-modeling -k shopping_cart_data
```

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"intro"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step2-astra"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>
