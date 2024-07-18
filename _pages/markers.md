---
title: "Brain Cell Atlas - Markers"
layout: homelay
excerpt: "Brain Cell Atlas -- Markers"
permalink: /markers/
---
<!-- <b>The page is under maintenance</b> -->
<html>
<head>
	<meta http-equiv="Content-type" content="text/html; charset=utf-8">
	<meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
	<link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.min.css">
	<link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/buttons/2.2.3/css/buttons.dataTables.min.css">
</head>
<body>
  <script type="text/javascript"  src="https://code.jquery.com/jquery-3.5.1.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
	<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
	<script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
	<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>

    <style>
		th {
        background-color: #23265F;
        background-color: #23265F;
        background-color: #23265F;
        color: rgba(255,255,255,0.9);
		    cursor: pointer;
        }
	</style>

<div class="container">
<!--b style="font-size: 24px;">
ATLAS
</b-->
<!--div class="shadow p-3 mb-5 bg-white rounded row"-->
<p><b>Step1</b> Click below to select a target dataset for different analysis.</p>
<div class="row" style="display: flex; justify-content: space-between;"> <!-- 两端对齐-->
<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Adult',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/adult-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F;">
ADULT BRAIN
</b>
</p>
</div>
</div>

<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Fetal',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/fetal-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F;">
FETAL BRAIN
</b>
</p>
</div>
</div>


<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Tumour',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/tumour-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F;">
TUMOR
</b>
</p>
</div>
</div>

<div class="col-lg-3 text-center custom-column">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Organoid',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/drganoid-brain.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px; color: #23265F;">
ORGANOID
</b>
</p>
</div>
</div>


<!--div class="col-lg-3 text-center">
<div class="img-circle card photo-card card-clickable" onclick="handleClick('Tumour',this)">
<img src="{{ site.url }}{{ site.baseurl }}/images/homePage/airway.png" class="rounded-circle" />
</div>
<div>
<p class="text-center" style="margin-top: 16px;">
<b style="font-size: 24px;">
ORGANOID
</b>
</p>
</div>
</div-->

</div>
</div>
<br/>
<div class="container">
<p><b>Step2</b> Click the buttons to show the differentially expressed genes (DEGs) of the target Brain Region or the target Cell type.</p>
  <button id="buttonA" onclick="changeOrder('A')">By Region</button>
  <button id="buttonB" onclick="changeOrder('B')">By Cell type</button>
</div>
  <br/>

<div class="container">
<p><b>Step3</b> Select the target Cell type/Region to show the DEGs.</p>
  <p id="sentence"></p>
  <select id="selectBox1" style="width: 200px; margin: 0 10px" onchange="handleSelectChange()"></select>
  <select id="selectBox2" style="width: 200px; margin: 5px" onchange="handleSelectChange()"></select>
  <!-- <button type="button" class="btn btn-primary btn-sm" onclick="toggleContent();displaySelectedImage();displaySelectedTable();">Markers</button> -->
  <button type="button" class="btn btn-primary btn-sm" style="text-transform: capitalize;" onclick="toggleContent();displaySelectedImage();displaySelectedTable();">Markers</button>
</div>
<br/>
<div id="contentContainer" style="display: none;">
<div class="container">
<div class="image-container">
<b>Result1</b> Volcano Plot.
<img id="selectedImage" src="" alt="Selected Image">
</div>
</div>
<br/>
<div class="container">
<b>Result2</b> The table of DEGs.
<div id="csvTableContainer" style="max-height: 500px; overflow-y: auto;"></div>
</div>
</div>
<script>
jQuery( document ).ready(function( $ ) {
        $(document).ready( function () {
        $.noConflict();
        var table = $('#mytable').DataTable();
        });
})
</script>

<div class="container">
<p id="clickMessageContainer" style="display: block;">Please click</p>
</div>


<!-- <div class="container">
<table id="myTable" class="display table table-striped table-bordered" cellspacing="0" width="100%">
<thead>
  <tr>
    <th>Year</th>
    <th>Author</th>
    <th>Title</th>
    <th>Ribozyme name</th>
    <th>Description</th>
    <th>Journal</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>2004</td>
    <td>Adams, P. L., M. R. Stahley, A. B. Kosek, J. Wang and S. A. Strobel </td>
    <td>Crystal structure of a self-splicing group I intron with both exons.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Crystal structure of <em>Azoarcus</em> group I intron with both exons</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/15175762"  target="_blank" ><b> Nature 430 (6995): 45-50.</b></a></td>
  </tr>
  <tr>
    <td>1989</td>
    <td>Flor, P. J., J. B. Flanegan and T. R. Cech </td>
    <td>A conserved base pair within helix P4 of the <em>Tetrahymena</em> ribozyme helps to form the tertiary structure required for self-splicing.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>The conserved base pair C109-G212 in P4 contributes to the tertiary structure required for self-splicing</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/2684642"  target="_blank" ><b> EMBO J 8 (11): 3391-9.</b></a></td>
  </tr>
  <tr>
    <td>1982</td>
    <td>Kruger, K., P. J. Grabowski, A. J. Zaug, J. Sands, D. E. Gottschling and T. R. Cech </td>
    <td>Self-splicing RNA: autoexcision and autocyclization of the ribosomal RNA intervening sequence of <em>Tetrahymena</em>.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Discovery</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/6297754"  target="_blank" ><b> Cell 31 (1): 147-57.</b></a></td>
  </tr>
  <tr>
    <td>1982</td>
    <td>Davies, R. W., R. B. Waring, J. A. Ray, T. A. Brown and C. Scazzocchio </td>
    <td>Making ends meet: a model for RNA splicing in fungal mitochondria.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Determination of shared secondary structure</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/6757759"  target="_blank" ><b> Nature 300 (5894): 719-24.</b></a></td>
  </tr>
  <tr>
    <td>1986</td>
    <td>Zaug, A. J. and T. R. Cech </td>
    <td>The intervening sequence RNA of <em>Tetrahymena</em> is an enzyme.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>The intervening sequence RNA of <em>Tetrahymena</em> is an enzyme</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/3941911"  target="_blank" ><b> Science 231 (4737): 470-5.</b></a></td>
  </tr>
  <tr>
    <td>1988</td>
    <td>Price, J. V. and T. R. Cech </td>
    <td>Determinants of the 3' splice site for self-splicing of the <em>Tetrahymena</em> pre-rRNA.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>ωG is closely related to the choice of 3' splice site</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/3209068"  target="_blank" ><b> Genes Dev 2 (11): 1439-47.</b></a></td>
  </tr>
  <tr>
    <td>1990</td>
    <td>Michel, F. and E. Westhof </td>
    <td>Modelling of the three-dimensional architecture of group I catalytic introns based on comparative sequence analysis.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>3D models of  group I intron based on comparative sequence analysis</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/2258934"  target="_blank" ><b> J Mol Biol 216 (3): 585-610.</b></a></td>
  </tr>
  <tr>
    <td>1996</td>
    <td>Cate, J. H., A. R. Gooding, E. Podell, K. Zhou, B. L. Golden, C. E. Kundrot, T. R. Cech and J. A. Doudna </td>
    <td>Crystal structure of a group I ribozyme domain: principles of RNA packing.</td>
    <td><a href="https://www.ribocentre.org/docs/groupI.html"  target="_blank" ><b> Group I self-splicing intron</b></a></td>
    <td>Crystal structure of <em>Tetrahymena</em> P4-P6 domain</td>
    <td ><a href="https://www.ncbi.nlm.nih.gov/pubmed/8781224"  target="_blank" ><b> Science 273 (5282): 1678-85.</b></a></td>
  </tr>
</tbody>
</table>
 -->
<style>
    .custom-column {
        margin: 0 50px; /* 设置列之间的间距 */
    }
</style>
<style>
  #csvTableContainer {
    max-height: 500px;
    overflow-y: auto;
  }

  /* 将表格头部固定 */
  #csvTableContainer thead {
    position: sticky;
    top: 0;
    background-color: white;
  }
</style>







<style>
   /* 设置固定宽度 */
  #selectBox1, #selectBox2 {
    width: 400px; /* 这里可以根据需要调整宽度 */
    height: 38px
  }
  .active {
    background-color: #23265F; 
    color: white;
  }
  .image-container {
    max-width: 100%;
    max-height: 100%;
    background-color: none;
    justify-content: center;
    align-items: center;
    box-shadow: none;
  }
  
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
/*   .table-container {
    max-height: 500px; 
    overflow-y: auto;
  } */
</style>
<script type="text/javascript"  src="https://code.jquery.com/jquery-3.5.1.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
<script type="text/javascript"  src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
<script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
<script type="text/javascript"  src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>
<script>
  var selectedImageId = null;
  var selectedOptions = [];
  var selectedButton = null;
  var selectBox1 = document.getElementById('selectBox1');
  var selectBox2 = document.getElementById('selectBox2');
  var originalOrder = true;
  var clickedCard = null;
  // document.addEventListener('DOMContentLoaded', function() {
  //   var adultButton = document.querySelector('.col-lg-3:nth-child(1) .card-clickable');
  //   adultButton.click();
  // });
  function handleClick(imageId,card) {
    if (clickedCard !== null) {
    clickedCard.classList.remove("clicked");
  }
    card.classList.add("clicked");
    clickedCard = card;
    selectedImageId = imageId;
    selectedOptions = [];
    fetch('{{ site.url }}{{ site.baseurl }}/js/genepage/RegionDEG.json')
      .then(response => response.json())
      .then(data => {
        var options = data[imageId];
        updateSelectBoxOptions('selectBox1', options);
        handleSelectChange(); // 确保选中第一个选项
      })
      .catch(error => {
        console.error('Error:', error);
      });
    fetch('{{ site.url }}{{ site.baseurl }}/js/genepage/CellTypeDEG.json')
      .then(response => response.json())
      .then(data => {
        var options = data[imageId];
        updateSelectBoxOptions('selectBox2', options);
        handleSelectChange(); // 确保选中第一个选项
      })
      .catch(error => {
        console.error('Error:', error);
      });
      // resetDisplay();
      displaySelectedImage()
  }
  function handleSelectChange() {
    var selectBox1 = document.getElementById('selectBox1');
    var selectBox2 = document.getElementById('selectBox2');
    var option1 = selectBox1.options[selectBox1.selectedIndex].value;
    var option2 = selectBox2.options[selectBox2.selectedIndex].value;
    selectedOptions = [option1, option2];
    resetDisplay();
    displaySelectedImage();
  }
  function resetDisplay() {
      var contentContainer = document.getElementById('contentContainer');
      var clickMessageContainer = document.getElementById('clickMessageContainer');
      contentContainer.style.display = 'none';
      clickMessageContainer.style.display = 'block';
    }
function displaySelectedImage() {
  if (selectedImageId !== null && selectedOptions.length === 2) {
    var imageName;
    if (selectedButton === 'A') {
      imageName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '.png';
    var imagePath = 'https://data.braincellatlas.org/volcano/VolcanoByRegion/' + imageName;
    } else if (selectedButton === 'B') {
      imageName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '.png';
    var imagePath = 'https://data.braincellatlas.org/volcano/VolcanoByCellType/' + imageName;
    }
    console.log('Image path:', imagePath); // 调试信息
    /* var imagePath = '{{ site.url }}{{ site.baseurl }}/images/markerPage/volcano/' + imageName; */
    // 在此处显示照片，例如：
    var imageElement = document.getElementById('selectedImage');
    imageElement.src = imagePath;
    imageElement.style.width = '500px';  // 设置宽度
    imageElement.style.height = 'auto';  // 高度自动调整
    // 设置图片居中
    imageElement.style.display = 'block';
    imageElement.style.margin = '0 auto';
    console.log('Selected Image:', imagePath);
  } else {
    console.log('Please select an image and options.');
  }
}
// function sortTable(columnIndex) {
//     var table = document.getElementById("your-table-id"); // 替换为你的表格的ID
//     var rows = Array.from(table.rows).slice(1); // 去掉表头，获取行数组 
//     // 根据指定的列索引进行排序
//     rows.sort(function(rowA, rowB) {
//         var cellA = rowA.cells[columnIndex].textContent.trim();
//         var cellB = rowB.cells[columnIndex].textContent.trim();
//         return cellA.localeCompare(cellB, "zh");
//     });
//     // 将排序后的行重新添加到表格中
//     rows.forEach(function(row) {
//         table.appendChild(row);
//     });
// }
// jQuery( document ).ready(function( $ ) {
//         $(document).ready( function () {
//         $.noConflict();
//         var table = $('#mytable').DataTable();
//         });
// })
function displaySelectedTable() {
  if (selectedImageId !== null && selectedOptions.length === 2) {
    var tableName;
    var tablePath;
    if (selectedButton === 'A') {
      tableName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '_cell_type.csv';
      tablePath = 'https://data.braincellatlas.org/markersByRegion/' + tableName;
    } else if (selectedButton === 'B') {
      tableName = selectedImageId + '_' + encodeURIComponent(selectedOptions[0]) + '_' + encodeURIComponent(selectedOptions[1]) + '_cell_type.csv';
      tablePath = 'https://data.braincellatlas.org/markersByCellType/' + tableName;
    } else {
      console.log('Please select an image and options.');
      return; // 结束函数的执行
    }
    console.log('Table Path:', tablePath);
    var xhr = new XMLHttpRequest();
    xhr.open('GET', tablePath, true);
    xhr.onreadystatechange = function() {
      if (xhr.readyState === 4 && xhr.status === 200) {
        var csvData = xhr.responseText;
        console.log('CSV Data:', csvData);
        var tableContainer = document.getElementById('csvTableContainer');
        // 解析 CSV 数据
        var rows = csvData.split('\n');
        var tableHtml = '<table id="mytable" class="mytable table table-striped table-bordered" cellspacing="0" width="100%">';
        var headerHtml = `<thead>
        <tr>
            <th>genes</th>
            <th>avg_log2FC</th>
            <th>p_val</th>
            <th>p_val_adj</th>
            <th>pct.1</th>
            <th>pct.2</th>
        </tr>
        </thead>
        <tbody>`;
        tableHtml += headerHtml;
        for (var i = 1; i < rows.length; i++) {
          var cells = rows[i].split(',');
          tableHtml += '<tr>';
          for (var j = 0; j < cells.length; j++) {
              // 去掉每个单元格内容的引号
              var cellContent = cells[j].replace(/^"(.*)"$/, '$1');
              tableHtml += '<td>' + cellContent + '</td>';
          }
          tableHtml += '</tr>';
        }
        tableHtml += `</tbody>
        </table>`;
        tableContainer.innerHTML = tableHtml;
        // 初始化表格并按第二列排序
        initializeDataTable();
      }
    };
    xhr.send();
  } else {
    console.log('Please select an image and options.');
  }
}
jQuery( document ).ready(function( $ ) {
        $(document).ready( function () {
        $.noConflict();
        var table = $('#mytable').DataTable();
        });
})
function initializeDataTable() {
  jQuery(document).ready(function($) {
    $.noConflict();
    $('#mytable').DataTable({
      "order": [[1, "asc"]] // 默认按第二列（索引1）升序排序
    });
  });
}
function updateSelectBoxOptions(selectBoxId, options) {
    var selectBox = document.getElementById(selectBoxId);
    selectBox.innerHTML = generateOptionsHtml(options);
    if (options.length > 0) {
        selectBox.value = options[0]; // 默认选中第一个选项
    }
  }
  function generateOptionsHtml(options) {
    var optionsHtml = '';
    for (var i = 0; i < options.length; i++) {
      optionsHtml += '<option value="' + options[i] + '">' + options[i] + '</option>';
    }
    return optionsHtml;
  }
document.addEventListener('DOMContentLoaded', function() {
    var buttonA = document.getElementById('buttonA');
    var buttonB = document.getElementById('buttonB');
    buttonA.click();
    // 设置按钮 A 为选中状态
    buttonA.classList.add('active');
    buttonB.classList.remove('active');
  });
  var activeButton = null;
  function changeOrder(button) {
    var sentenceElement = document.getElementById("sentence");
    var buttonA = document.getElementById('buttonA');
    var buttonB = document.getElementById('buttonB');
    if (button === 'A') {
      buttonA.classList.add('active');
      buttonB.classList.remove('active');
      activeButton = buttonA;
      sentenceElement.innerHTML = 'Search for <b>differentially expressed genes (DEGs)</b> of selected cell type compared to others in the selected respiratory system region.';
      selectedButton = button;
      originalOrder = true;
      resetSelectBoxes();
    } else if (button === 'B') {
      buttonA.classList.remove('active');
      buttonB.classList.add('active');
      activeButton = buttonB;
      sentenceElement.innerHTML = 'Search for <b>differentially expressed genes (DEGs)</b> of selected respiratory system region compared to others in the selected cell type.';
      selectedButton = button;
      originalOrder = false;
      resetSelectBoxes();
      resetDisplay();
    }
 }   
  function resetSelectBoxes() {
    if (originalOrder) {
      selectBox1.parentNode.insertBefore(selectBox1, selectBox2);
    } else {
      selectBox2.parentNode.insertBefore(selectBox2, selectBox1);
    }
  }
  function toggleContent() {
    var contentContainer = document.getElementById('contentContainer');
    var clickMessageContainer = document.getElementById('clickMessageContainer');
    if (contentContainer.style.display === 'none') {
      contentContainer.style.display = 'block';
      clickMessageContainer.style.display = 'none';
    } else {
      contentContainer.style.display = 'none';
      clickMessageContainer.style.display = 'block';
    }
  }


</script>

<script>
  $(document).ready( function () {
    $.noConflict();
    var table = $('#mytable').DataTable();
} );
</script>

<script>
function showImage0(photoName) {
    var photoElement = document.getElementById('photo');
    photoElement.src = photoName;
    photoElement.alt = photoName;
  }
</script>
<style>
  .image-container {
    max-width: 100%;
    max-height: 100%;
    background-color: none;
    justify-content: center;
    align-items: center;
    box-shadow: none;
  }
  
  .image-container img {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
  .container {
  /* background-color: #f0f0f0; */ /* 设置背景颜色为您想要的颜色值 */
  box-shadow: 0 0 15px grey;
  border-radius: 10px; /* 设置边框圆角的半径，可以根据需要进行调整 */
  padding: 10px; /* 可选：添加内边距以增加内容与边框之间的间距 */
}
  #buttonA, #buttonB {
      font-size: 17px; /* Increase font size */
      /* padding: 15px 30px; /* Increase padding */
      margin: 5px; /*Add some margin*/
      width: 150px; /*Set button width  */
      height: 38px; /* Set button height */
      /* cursor: pointer;
      border: none;
      background-color: #23265F; /* Change background color */
      /* color: white; Change text color */
      /* border-radius: 5px; Add border radius  */
    }
    /* #buttonA:hover, #buttonB:hover {
      background-color: #23265F; Change background color on hover */
    /* } */
</style>
<style>
    .photo-card {
/*         width: 200px;
        height: 200px; */
        border: 10px solid #ccc; 
        overflow: hidden;
        border-radius: 50%;
        position: relative;
        background-size: cover;
 /*        display: flex;  
        justify-content: right; /* 水平居中对齐 */
        /* align-items: right;  */
    }
    .photo-card:hover img {
        transform: scale(1.1);
    }
    .photo-card img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: transform 0.3s;
    }
    .photo-card.clicked {
        border-color: #23265F;
    }
</style>
</body>
<style>
    .btn-primary {
      font-weight: normal; /* 确保文本不加粗 */
      font-size: 17px;    /* 设置文本字体大小 */
    }
  </style>