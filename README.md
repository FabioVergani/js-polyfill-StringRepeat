# js-polyfill-StringRepeat

var o=String.prototype, f=o.repeat;
if(!f){
 (function(x){'use strict';
  function r(n){
   var i=n,t='',s=this;
   if(s===null){
    throw TypeError();
   }else{
    s=String(s);
	if(s.length!==0){
	 i=Number(i);
	 if((i<0)||(i===Infinity)){
	  throw RangeError();
	 }else{
      if(i>1){while(i){t+=s;--i;};}else{if(i===1){t=s}};
      s=t;
	 };
    };
    return t;
   };
  };
  if(f=Object.defineProperty){f(x,'repeat',{'value':r,'configurable':true,'writable':true});}else{o.repeat=r;};
 })(o);
};
//use:
console.log("1".repeat(0));
console.log("1".repeat(11));
console.log("".repeat(11));
console.log("".repeat(0));
