# example2 : avail\_from = avail\_data\_method

```markup
<criteria id="product_id_list"  view_type="select" is_required="true" label="Product ID" pre_criteria="product_group_list" result_args="product_id_list"  next_criteria="step_group_list" avail_data_method.args="product_group_list">
        <select_opt view_type="multiple" avail_from="avail_data_method" avail_data_method="get_avail_product_id_list"/>                                                                         
</criteria>
```

