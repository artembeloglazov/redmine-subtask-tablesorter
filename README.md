redmine-subtask-tablesorter
=========

## 1 шаг
Добавляем css:

```css
/* TABLE SORT */
/* https://github.com/artembeloglazov/tablesort */

/* tables */
table.tablesorter {
        font-family:arial;
        background-color: #CDCDCD;
        margin:10px 0pt 15px;
        font-size: 8pt;
        width: 100%;
        text-align: left;
}
table.tablesorter thead tr th, table.tablesorter tfoot tr th {
        background-color: #e6EEEE;
        border: 1px solid #FFF;
        font-size: 8pt;
        padding: 4px;
}
table.tablesorter thead tr .header {
        background-image: url("https://raw.github.com/artembeloglazov/tablesort/master/bg.gif");
        background-repeat: no-repeat;
        background-position: center right;
        cursor: pointer;
}
table.tablesorter tbody td {
        color: #3D3D3D;
        padding: 2px;
        background-color: #FFF;
        vertical-align: top;
}
table.tablesorter tbody tr.odd td {
        background-color:#F0F0F6;
}
table.tablesorter thead tr .headerSortUp {
        background-image: url("https://raw.github.com/artembeloglazov/tablesort/master/asc.gif");
}
table.tablesorter thead tr .headerSortDown {
        background-image: url("https://raw.github.com/artembeloglazov/tablesort/master/desc.gif");
}
table.tablesorter thead tr .headerSortDown, table.tablesorter thead tr .headerSortUp {
   background-color: #8dbdd8;
}

```

## 2 шаг
Добавляем javascript:

```javascript
// redmine-subtask-tablesorter https://github.com/artembeloglazov/redmine-subtask-tablesorter
$( document ).ready(function() {

   $('#issue_tree p strong:contains("Подзадачи")').append(' (кол-во: ' + $('#issue_tree .issue.hascontextmenu').length + ', из них закрытые: ' + $('#issue_tree .issue.hascontextmenu > td:contains("Закрыта")').length + ')');
   $('#issue_tree table.list.issues').attr('id', 'subTaskTable').addClass('tablesorter');
   $('.controller-issues #content table:has(th):not(.attributes)').prepend('<thead></thead>');
   $('.controller-issues #content table:has(th):not(.attributes)').each(function(){
        $(this).find('thead').wrapInner($(this).find('tbody tr:first-child'));
   });
   $('#subTaskTable tbody').first().before('<thead><th style="display:none">111</th><th>name</th><th>status</th><th>author</th><th>progress</th></thead>');
   $.getScript("http://rawgithub.com/artembeloglazov/redmine-subtask-tablesorter/master/jquery.tablesorter.min.js", function(){
     $('#subTaskTable').tablesorter();
     $('.controller-issues #content table:has(th):not(.attributes)').each(function(){
          $(this).tablesorter();
     });
     $('.controller-issues th.header').css( 'cursor', 'pointer' );
   });

});
```
