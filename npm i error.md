### error

Error: EPERM: operation not permiError: EPERM: operation not permitted, renametted, rename....

- - - 
这个问题在stackoverfow上有解决的方法，我就不重复复制粘贴了。
我的方法是最简单粗暴的。
当你npm install   xxx  --save  报错如上面的时候，把--save去掉，直接install  然后手动在package.json中进行添加就好了。

- - -
恩，就这样。
