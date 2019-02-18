<?php
include 'list.php'; 
    /* include the to do list file */

$status = 'all'; 
    /* status can be changed to true, false, or 'all' depending on the information that need to be displayed */
$field = 'priority'; 
    /* 1 being the highest priority, change in todo.php */
$filter = array();

foreach($list as $originalKey => $item){
    if ($status === 'all' || $item['complete'] == $status){
        if (isset($field) && isset ($item[$field])){
            $filter[$originalKey] = $item[$field];
        } else {
            $filter[$originalKey] = $item['priority']+12; 
                /* Place items without due dates after those with due dates */
        }
    }
}
asort($filter);

/********************
*** Var Dump Code ***
********************/

/*
echo '<pre>';
var_dump($filter);
echo '</pre>';
*/

echo '<table>';
echo '<tr>';
echo '<th>Title</th>';
echo '<th>Priority</th>';
echo '<th>Due Date</th>';
echo '<th>Complete</th>';
echo '</tr>';
foreach($filter as $id => $value){
    echo '<tr>';
    echo '<td>' .$list[$id]['title'] . "</td>\n";
    echo '<td>' .$list[$id]['priority'] . "</td>\n";
    echo '<td>' .$list[$id]['due'] . "</td>\n";
    echo '<td>';
    if ($list[$id]['complete']){
        echo 'Yes';
    }else{
        echo 'No';
    }
    echo "</td>\n";
    echo '</tr>';
}
echo '</table>';
?>
