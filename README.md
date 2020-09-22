<div align="center">

## Page Protector \- High security HTML encryptor


</div>

### Description

Page Protector is a high security encryptor for protecting your HTML pages, it uses HEX encryption, and as a bonus the decrpytion code is also encrypted so it's more hard to break the code.

If you like my code PLEASE VOTE and/or POST YOUR COMMENTS PLEASE :)
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Design7 Software](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/design7-software.md)
**Level**          |Intermediate
**User Rating**    |4.6 (32 globes from 7 users)
**Compatibility**  |
**Category**       |[Security](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/security__2-74.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/design7-software-page-protector-high-security-html-encryptor__2-3218/archive/master.zip)





### Source Code

```
<html>
<head>
<style>
.form_skin{border:1px solid; font-family:Arial; font-size:12px;}
</style>
<meta http-equiv="Content-Type" content="text/html; charset=windows-1252">
<meta name="GENERATOR" content="Microsoft FrontPage 4.0">
<meta name="ProgId" content="FrontPage.Editor.Document">
<title>Page Protector</title>
</head>
<body>
<script language="JavaScript">
var decode='function dc(e){var ds="";for(i=0;i<e.length;i+=2){' +
'ds+=String.fromCharCode(parseInt(e.substring(i,i+2), 16));}return ds;}document.write(dc(ep));';
function ec(s){
//Function to encrypt any string with byte ranges from 0 To 255
var es="", ct="", nc;
//Build ASCII table
for(c=0;c<=255;c++) ct+=String.fromCharCode(c);
for(i=0;i<s.length;i++){
//Convert the ASCII key code of the
//current char to its hexadecimal equivalent
nc=ct.indexOf(s.charAt(i)).toString(16);
//If hex string is not 2 chars then add a 0 before it
if(nc.length!=2) nc="0"+nc;
es+=nc;
}
return es;
}
function dc(e){
//Function to decrypt string encrypted with HEX encryption
var ds="";
for(i=0;i<e.length;i+=2){
//Get two chars and then convert them
//from hexadecimal to an ASCII char
ds+=String.fromCharCode(parseInt(e.substring(i,i+2), 16));
}
return ds;
}
function encrypt(){
window.status="Encrypting page...";
var pagecontent=document.pageprotector.pagehtml.value;
document.pageprotector.pagehtml.value=ec(pagecontent);
window.status="";
}
function decrypt(){
window.status="Decrypting page...";
var pagecontent=document.pageprotector.pagehtml.value;
document.pageprotector.pagehtml.value=dc(pagecontent);
window.status="";
}
function protectpage(){
var pagecontent=document.pageprotector.pagehtml.value;
//Build the encrypted page, also note that the decryption
//code is also encrypted using the escape method
var protected="<html><body><script>var ep=\"" + pagecontent + "\";eval(unescape(\"" + escape(decode) + "\"));<\/script><\/body><\/html>";
document.pageprotector.pagehtml.value=protected;
document.pageprotector.pagehtml.focus();
window.status="";
alert("Page was protected succesfully");
}
function selectall(){
document.pageprotector.pagehtml.focus();
document.pageprotector.pagehtml.select();
}
</script>
<form name="pageprotector">
 <p><textarea rows="10" name="pagehtml" cols="89" class="form_skin"></textarea></p>
 <p><input type="button" value="   Encrypt   " name="B1" onClick="encrypt();" class="form_skin">&nbsp;
 <input type="button" value="  Decrypt  " name="B2" onClick="decrypt();" class="form_skin">&nbsp;
 <input type="button" value="  Protect page  " name="B3" onClick="protectpage();" class="form_skin">&nbsp;
 <input type="button" value="   Select All  " name="B4" onClick="selectall();" class="form_skin"></p>
</form>
</body>
</html>
```

