<!-- TOP -->
<div class="top">
  <img src="https://datastax-academy.github.io/katapod-shared-assets/images/ds-academy-logo.svg" />
  <div class="scenario-title-section">
    <span class="scenario-title">Tables with Single-Row Partitions in Apache Cassandra®</span>
    <span class="scenario-subtitle">ℹ️ For technical support, please contact us via <a href="mailto:aleksandr.volochnev@datastax.com">email</a> or <a href="https://dtsx.io/aleks">LinkedIn</a>.</span>
  </div>
</div>

<!-- NAVIGATION -->
<div id="navigation-top" class="navigation-top">
 <a href='command:katapod.loadPage?[{"step":"step3-astra"}]'
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 4 of 10</span>
 <a href='command:katapod.loadPage?[{"step":"step5-astra"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Design query Q1</div>

✅ Find id and name of an active shopping cart that belongs to user `jen`:
 
<details>
  <summary>Solution 1 (preferred)</summary>

```
-- Retrieve all carts for jen
-- and scan the result set
-- within an application
-- to find an active cart.
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen';
```

</details>

<br/>

<details>
  <summary>Solution 2</summary>

```
-- Retrieve all carts for jen
-- and scan the result set
-- within Cassandra
-- to find an active cart.
-- Note that this is a rare case of
-- scanning within a small partition
-- when ALLOW FILTERING 
-- might be acceptable. 
SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen'
  AND cart_is_active = true 
ALLOW FILTERING;
```

</details>

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"step3-astra"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step5-astra"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>

