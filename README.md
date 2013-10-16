tablesort
=========
```javascript
$('#issue_tree table.list.issues').attr('id', 'subTaskTable')
$('#subTaskTable').append('<thead><th>name</th><th>status</th><th>author</th><th>progress</th></thead>')
$.getScript("http://redmine.rg1.ru/custom_js/jquery.tablesorter.min.js", function(){
  $('#subTaskTable').tablesorter();
});
```
очистить заголовки:

```javascript
$('#subTaskTable').remove()
```
