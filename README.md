yii-CMemCacheSASL
=================

A Yii memcache component with SASL support, mainly built for heroku.

This component uses [ronnywang's PHPMemcacheSASL](https://github.com/ronnywang/PHPMemcacheSASL) implementation.

To learn more, read the blog post here: [http://aaronfrancis.com/blog/2013/4/9/some-thoughts-about-hosting-yii-on-heroku](http://aaronfrancis.com/blog/2013/4/9/some-thoughts-about-hosting-yii-on-heroku)


````
'components'=>array(
  'cache'=>array(
    'class'=>'CMemCache',
    'server'=> array(
      'host'=>'mc7.ec2.northscale.net',
      'port'=>11211,
      'password'=>'8WO234qKhb7O8vnm',
      'username'=>'app123367982%40heroku.com'
    ),
  ),
)
````

Or if on Heroku

````
'components'=>array(
  'cache'=>array(
    'class'=>'CMemCache',
    'server'=> array(
      'host'=>getenv('MEMCACHE_SERVERS'),
      'port'=>11211,
      'password'=>getenv('MEMCACHE_PASSWORD'),
      'username'=>getenv('MEMCACHE_USERNAME')
    ),
  ),
)
````


I haven't tested it very much, so please provide feedback if you use it.
