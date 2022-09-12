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
 <a href='command:katapod.loadPage?[{"step":"step5-cassandra"}]'
   class="btn btn-dark navigation-top-left">⬅️ Back
 </a>
<span class="step-count"> Step 6 of 10</span>
 <a href='command:katapod.loadPage?[{"step":"step7-cassandra"}]' 
    class="btn btn-dark navigation-top-right">Next ➡️
  </a>
</div>

<!-- CONTENT -->

<div class="step-title">Design update U2</div>

✅ Save an active shopping cart with name `My Birthday` and id `4e66baf8-f3ad-4c3b-9151-52be4574f2de`, 
and designate a different cart with name `Gifts for Mom` and id `19925cc1-4f8b-4a44-b893-2a49a8434fc8` to be a new active shopping cart for user `jen`:

<details>
  <summary>Solution</summary>

```
BEGIN BATCH
  UPDATE carts_by_user 
  SET cart_is_active = false
  WHERE user_id = 'jen'
    AND cart_name = 'My Birthday'
    AND cart_id = 4e66baf8-f3ad-4c3b-9151-52be4574f2de
  IF cart_is_active = true;
  UPDATE carts_by_user 
  SET cart_is_active = true
  WHERE user_id = 'jen'
    AND cart_name = 'Gifts for Mom'
    AND cart_id = 19925cc1-4f8b-4a44-b893-2a49a8434fc8;
APPLY BATCH;

SELECT user_id, cart_name, 
       cart_id, cart_is_active
FROM carts_by_user
WHERE user_id = 'jen';
```

</details>

<!-- NAVIGATION -->
<div id="navigation-bottom" class="navigation-bottom">
 <a href='command:katapod.loadPage?[{"step":"step5-cassandra"}]'
   class="btn btn-dark navigation-bottom-left">⬅️ Back
 </a>
 <a href='command:katapod.loadPage?[{"step":"step7-cassandra"}]'
    class="btn btn-dark navigation-bottom-right">Next ➡️
  </a>
</div>

