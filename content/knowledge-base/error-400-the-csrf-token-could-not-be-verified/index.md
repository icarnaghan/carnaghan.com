---
author: "icarnaghan"
title: "Error 400: The CSRF token could not be verified"
date: 2018-03-22
---

Getting _**Error 400: The CSRF token could not be verified.**_ when trying to delete an item using the default delete link.

$this->menu=array( array('label'=>'Create Use', 'url'=>array('create')), array('label'=>'Update Use', 'url'=>array('update', 'id'=>$model->use\_id)), **array('label'=>'Delete Use', 'url'=>'#', 'linkOptions'=>array('submit'=>array('delete','id'=>$model->use\_id,'confirm'=>'Are you sure you want to delete this item?')),** array('label'=>'Manage Uses', 'url'=>array('admin')), );

**Answer**:

This problem can be solved by adding **'csrf' => true** to the linkOptions

$this->menu=array( array('label'=>'Create Use', 'url'=>array('create')), array('label'=>'Update Use', 'url'=>array('update', 'id'=>$model->use\_id)), array('label'=>'Delete Use', 'url'=>'#', 'linkOptions'=>array('submit'=>array('delete','id'=>$model->use\_id,'confirm'=>'Are you sure you want to delete this item?')**,'csrf'=>true)**), array('label'=>'Manage Uses', 'url'=>array('admin')), );
