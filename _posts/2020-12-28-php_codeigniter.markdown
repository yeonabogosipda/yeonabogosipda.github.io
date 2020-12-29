---
layout: post
title: php
date: 2020-12-28 12:00
comments: true
external-url:
categories: programming
---

> php에서 codeigniter의 중요성

codeigniter model 예제

```php
<?php class Test_model extends CI_Model{ 
function __construct() 
	{ 
		parent::__construct(); 
	} 
	function gets(){ 
	$strQuery = "SELECT * FROM test"; return $this->db->query($strQuery)->result(); 
	} 
	function get1($seq){ 
	$strQuery = "SELECT * FROM test where seq = " . $seq; return $this->db->query($strQuery)->result(); 
	} 
	function get2($seq){ 
	return $this->db->get_where('test',array('seq'=>$seq))->row(); 
	} 
} ?>


```


