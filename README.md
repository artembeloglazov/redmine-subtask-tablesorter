tablesort
=========

## 1 шаг
Добавляем css на страницу: https://raw.github.com/artembeloglazov/tablesort/master/style.css

## 2 шаг

```javascript
$('#issue_tree table.list.issues').attr('id', 'subTaskTable').addClass('tablesorter');
$('#subTaskTable tbody').first().before('<thead><th style="display:none">111</th><th>name</th><th>status</th><th>author</th><th>progress</th></thead>');
$.getScript("http://redmine.rg1.ru/custom_js/jquery.tablesorter.min.js", function(){
  $('#subTaskTable').tablesorter();
});
```

## очистить заголовки:

```javascript
$('#subTaskTable').remove()
```
