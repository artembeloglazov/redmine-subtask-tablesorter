tablesort
=========
```javascript
$('head').append('<link rel="stylesheet" href="https://raw.github.com/artembeloglazov/tablesort/master/style.css" type="text/css" />');
$('#issue_tree table.list.issues').attr('id', 'subTaskTable').addClass('tablesorter');
$('#subTaskTable').append('<thead><th>name</th><th>status</th><th>author</th><th>progress</th></thead>');
$.getScript("http://redmine.rg1.ru/custom_js/jquery.tablesorter.min.js", function(){
  $('#subTaskTable').tablesorter();
});
```
очистить заголовки:

```javascript
$('#subTaskTable').remove()
```
