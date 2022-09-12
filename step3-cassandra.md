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
 <a href='command:katapod.loadPage?[{"step":"step2-cassandra"}]' 
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 3 of 10</span>
 <a href='command:katapod.loadPage?[{"step":"step4-cassandra"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Populate tables</div>

✅ Execute the CQL script to insert sample data:
```
SOURCE 'assets/shopping_cart_data.cql'
```

✅ Retrieve all rows from table `carts_by_user`:
```
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user;        
```

✅ Retrieve all rows from table `items_by_id`:
```
SELECT * FROM items_by_id;
```

✅ Retrieve all rows from materialized view `items_by_name`:
```
SELECT * FROM items_by_name;                    
```

✅ Retrieve all rows from table `items_by_cart`:
```
SELECT cart_id, timestamp, item_id 
FROM items_by_cart; 

SELECT cart_id, item_id, item_price, 
       quantity, cart_subtotal 
FROM items_by_cart; 
```

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"step2-cassandra"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step4-cassandra"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>
