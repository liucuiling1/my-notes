#### tabindex属性的作用

* 当tabindex=0时，该元素可以用tab键获取焦点  
* 当tabindex=-1时，该元素用tab键获取不到焦点，但是可以通过js获取  
* 当tabindex>=1时，该元素可以用tab键获取焦点，而且优先级大于tabindex=0；不过在tabindex>=1时，数字越小，越先定位到。  