stylus-scoped-media-query
=========================

Stylus port of the Filament Group's Sass mixin


### Mixin:

``` Stylus
scope-media-query( queries... )

    max = length( queries )
    min = 1

    for query in ( min..max )

        if query % 2 == 1

            threshold  = queries[(query - 1)]
            selector   = queries[query]

            @media threshold
                {selector} 
                    {block}
```

### Sample Usage:

``` Stylus
 +scope-media-query( 
	'(min-width : 30em)', '.content', 
	'(min-width : 90em)', '.aside' )
	
	.first-class
	  border  1px solid blue

	.second-class
	  width   50%

```

### Sample Output:

``` CSS
@media (min-width : 30em) {
  .content .first-class {
    border: 1px solid #00f;
  }
  .content .second-class {
    width: 50%;
  }
}
@media (min-width : 90em) {
  .aside .first-class {
    border: 1px solid #00f;
  }
  .aside .second-class {
    width: 50%;
  }
}
```



