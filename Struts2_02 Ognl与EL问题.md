# el与ognl解析问题

1. EL使用的符号为: ${}, OGNL使用符号为%{};
2. 使用EL只可以获取4大域的对象, 使用get方式提交的数据不可以使用request获取, 要使用${param.name}获取;

# Request请求数据/setAttribute数据搞混淆

1. 他们不是一回事, 使用EL或者OGNL获取4大域的值, 只可以获取setAttribute的值;
2. 而请求的值虽然在Request对象中但是并不可以在页面直接获取,
   1.  在struts2中可以使用HttpParameters来获取, parameter方便获取值;
   2. 传统的servlet中使用getParameter()或者getParameterNames()来获取;
   3. jsp中使用EL获取: ${param.key}
   4. jsp中使用OGNL: %{parameters.key}

# ActionContext的实例方法put()方法;

1. 他将数据以key-value的形式放入ActionContext中, 而不是request, 但是这与request很像, 所以可以代替ActionContext;