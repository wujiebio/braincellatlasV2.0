---
title: "Brain Cell Atlas - Database"
layout: textlay
excerpt: " The Databases in Brain Cell Atlas, GZNL-RDC. "
sitemap: true
permalink: /database/
---
<html lang="en">
<head>
<!--set sort order in table header begin-->
<meta http-equiv="Content-type" content="text/html; charset=utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1,user-scalable=no">
  <!-- <title>Ribozyme applications</title> -->
  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/1.12.1/css/jquery.dataTables.min.css">
  <link rel="stylesheet" type="text/css" href="https://cdn.datatables.net/buttons/2.2.3/css/buttons.dataTables.min.css">
<script type="text/javascript" src="https://code.jquery.com/jquery-3.5.1.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/1.12.1/js/jquery.dataTables.min.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/dataTables.buttons.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jszip/3.1.3/jszip.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/pdfmake.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/pdfmake/0.1.53/vfs_fonts.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.html5.min.js"></script>
    <script type="text/javascript" src="https://cdn.datatables.net/buttons/2.2.3/js/buttons.print.min.js"></script>
    <script src="https://cdn.plot.ly/plotly-latest.min.js"></script>
  <!--set sort order in table header finish-->
  <!-- <style>
    .header_box {
    border: none;
    background: #efefef;
    font-size:24px
  }
  h2{
    font-size:20px;
    font-weight: bold;
  }
/* Button Container Styles */
    .button-container {
      display: flex;
      justify-content: left;
      align-items: center;
      height: 50px;
      overflow:auto
    }
    /* Button Style */
    .button {
      display: block;
      padding: 10px;
      margin-right: 10px;
      text-align: center;
      background-color: #efefef;
      color: #005826;
      text-decoration: none;
      font-size: 16px;
      border: 1px solid #005826;
      border-radius: 5px;
    }
    /* Mouse Hover Style */
    .button:hover {
      background-color: #999;
      cursor: pointer;
    }
    /* 样式表格 */
    table {
        border: 2px solid #f8f8ff;
        border: 2px solid #767676;
		    border: 2px solid #767676;
		    border-radius: 5px;
		    background-color: #fff;
		    border-radius: 0;
        }
		  th {
        background-color: #719B71;
        background-color: #719B71;
        background-color: #005826;
        color: rgba(255,255,255,0.9);
		    cursor: pointer;
        }
		  td {
		    background-color: #ffffff;
		    background-color: #f9f9f9;
		    background-color: #f9f9f9;
		    }		
		  th, td {
		  padding: 10px 10px;
		}
    /* 隐藏所有 sheet */
    .sheet {
      display: none;
      overflow:auto
    }
    /* Style the search box */
  #searchBox {
    padding: 10px;
    font-size: 16px;
    border: 2px solid #ccc;
    border-radius: 4px;
    width: 300px;
  }
  /* Style the search box when it has focus */
  #searchBox:focus {
    outline: none;
    border-color: #2354C4;
  }
  /* Style the placeholder text */
  #searchBox::placeholder {
    font-size: 16px;
  }
  /* 搜索框和下载框水平布局 */
    .form-container {
      display: flex;
      align-items: center;
      overflow:auto
    }
    .form-container input {
      margin-right: 10px;
    }
    /* 下载框位置设置 */
    .form-container select {
      margin-left: auto;
      padding: 10px;
      font-size: 16px;
      border: 2px solid #ccc;
      border-radius: 4px;
      width: 300px;
    }
    .button.clicked {
    background-color: #999;
}

<!--   </style> -->
</head> 

<!-- <body onload="showSheet('sheet1')"> -->
<!-- 
<p class="header_box" >Detail information</p>

        
This section lists all the experimentally validated riboswitches. -->
<div style="text-align: right;">
<input type="text" id="searchBox" placeholder="Search by keyword..." onfocus="showAllSheets()" oninput="searchTables()"><br><br>
</div>
<div>
<table id="cfttable" class="table table-hover table-bordered">
    <colgroup>
          <col style="width: 20%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 5%;">
          <col style="width: 20%;">
          <col style="width: 5%;">
          <col style="width: 10%;">
          <col style="width: 5%;">
          <col style="width: 10%;">
          <col style="width: 10%;">
          <col style="width: 10%;">
          <!-- <col style="width: 5%;"> -->
        </colgroup>
        <thead>
        <tr>
          <th onclick="sortTable(0)">Species</th>
          <th onclick="sortTable(1)">Atlas</th>
          <th onclick="sortTable(2)">Tissue</th>
          <th onclick="sortTable(3)">Status</th>
          <th onclick="sortTable(4)">Platform</th>
          <th onclick="sortTable(5)">Seq-type</th>
          <th onclick="sortTable(6)">Year</th>
          <th onclick="sortTable(7)">Accession</th>
          <th onclick="sortTable(8)">Link</th>
          <th onclick="sortTable(9)">Datasets</th>
          <th onclick="sortTable(10)">DOI</th>
          <th onclick="sortTable(11)">Download</th>
        </tr>
        </thead>
<tbody>
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Multiple sclerosis</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">PRJNA544731</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/bioproject/PRJNA544731" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Microglia_Schirmer_2019_10x</td>
      <td name="td11">10.1038/s41586-019-1404-z</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbbJ9WG3bZFFvMkeJ9sIbi4B_khSeTAzvZrLdXePmH7T9Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Motor cortex</td>
      <td name="td3">Amyotrophic lateral sclerosis</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE174332</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE174332" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_motor_cortex_Pineda_2021_10x</td>
      <td name="td11">10.1101/2021.07.07.451374</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeMVdUaB4CVBvgTDPdsVF-cBzvX3EL56jH7dGZOJFjSJlg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Motor cortex</td>
      <td name="td3">Frontotemporal lobar degeneration</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE174332</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE174332" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_motor_cortex_Pineda_2021_10x</td>
      <td name="td11">10.1101/2021.07.07.451374</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeMVdUaB4CVBvgTDPdsVF-cBzvX3EL56jH7dGZOJFjSJlg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Autism spectrum disorder</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">PRJNA434002</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/bioproject/PRJNA434002" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Velmeshev_2019</td>
      <td name="td11">10.1126/science.aav8130</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaWMA3DGZJ1DkhpIYx7XFyUBiEOMkID9ELk8BvdwOOgpDw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">White matter</td>
      <td name="td3">Multiple sclerosis</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118257</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118257" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_WhiteMatter_Jakel_2019_10x</td>
      <td name="td11">10.1038/s41586-019-0903-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZBis1gC3IJCmAEqMmbWuFcBYrfUYS2tbKnxbXNheArhBg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Brain vasculature</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE160936</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE160936" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Microglia_Tsartsalis_2021_10x</td>
      <td name="td11">10.1101/2021.10.27.465860</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EV158kWFJ4xJgNc_JEDQaJUBIDFKaaPs0pwZr0FpPfbITQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Substantia nigra</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE140231</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE140231" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_FC_Agarwal_2020_10x</td>
      <td name="td11">10.1038/s41467-020-17876-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eexz2c1_EH1DruENkp8uHK0B91BlsfhsSekL4QpC610H4A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Ganglionic eminences</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE135827</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE135827" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Ganglionic_eminences_Shi_2021_10x</td>
      <td name="td11">10.1126/science.abj6641</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeV2ML_LdilBqvr1q0kpP4sBUoJDY35S28OKAtaqoD40uA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE173279</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE173279" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBMs_LeBlanc_2021_10x</td>
      <td name="td11">10.1016/j.ccell.2022.02.016</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfZKW8512NlKsvS6nqcOPTEBEfGwXI8tEdIP5tF_EQO0ag?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE173278</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE173278" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBMs_LeBlanc_2021_10x</td>
      <td name="td11">10.1016/j.ccell.2022.02.016</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfZKW8512NlKsvS6nqcOPTEBEfGwXI8tEdIP5tF_EQO0ag?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Organoid</td>
      <td name="td3">Glioma</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE193884</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE193884" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBMs_LeBlanc_2021_10x</td>
      <td name="td11">10.1016/j.ccell.2022.02.016</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfZKW8512NlKsvS6nqcOPTEBEfGwXI8tEdIP5tF_EQO0ag?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE117891</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE117891" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glioma_Yu_2020_STRTseq</td>
      <td name="td11">10.1093/nsr/nwaa099</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EesBs7IFmhdFmrSKavpIknYBlj4dRKGhFRexo8zlZMw8Uw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Spinal cord</td>
      <td name="td3">Multiple sclerosis</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130105</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE130105" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_Wheeler_2020_DropSeq_10x</td>
      <td name="td11">10.1038/s41586-020-1999-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbrfEyj2uD1Hgs9gm9OJtOsBroVD8a2rHSlRm5vsHzU9xA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Brain</td>
      <td name="td3">Multiple sclerosis</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130105</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE130105" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_Wheeler_2020_DropSeq_10x</td>
      <td name="td11">10.1038/s41586-020-1999-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbrfEyj2uD1Hgs9gm9OJtOsBroVD8a2rHSlRm5vsHzU9xA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Brain vasculature</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="http://compbio.mit.edu/scADbbb/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_CV_SunN_2022_10x</td>
      <td name="td11">10.1101/2022.02.09.479797</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ERhQdUp-ZhdGmkh9sEfdDRkBcgrA1J5I0AQgdON9ArlcaA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">SCR_015820</td>
      <td name="td8"><a href="https://scicrunch.org/scicrunch/Resources/record/nlx_144509-1/SCR_015820/resolver" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_wholebrain_Siletti_2022_10x</td>
      <td name="td11">10.1101/2022.10.12.511898</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaijWmMnR35MvrHr4PRYkqkBjrdPPuQMhKu63AYV6rUyqg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">jhpce#tran2021</td>
      <td name="td8"><a href="https://github.com/LieberInstitute/10xPilot_snRNAseq-human" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Tran_2021</td>
      <td name="td11">10.1016/j.neuron.2021.09.001</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EedZ-939p7BNtHrbnCRiVBIBWLbK0GNoCpz82i75JTVkWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Basal ganglia</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">jhpce#tran2021</td>
      <td name="td8"><a href="https://github.com/LieberInstitute/10xPilot_snRNAseq-human" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Tran_2021</td>
      <td name="td11">10.1016/j.neuron.2021.09.001</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EedZ-939p7BNtHrbnCRiVBIBWLbK0GNoCpz82i75JTVkWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">jhpce#tran2021</td>
      <td name="td8"><a href="https://github.com/LieberInstitute/10xPilot_snRNAseq-human" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Tran_2021</td>
      <td name="td11">10.1016/j.neuron.2021.09.001</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EedZ-939p7BNtHrbnCRiVBIBWLbK0GNoCpz82i75JTVkWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Amygdala</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">jhpce#tran2021</td>
      <td name="td8"><a href="https://github.com/LieberInstitute/10xPilot_snRNAseq-human" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Tran_2021</td>
      <td name="td11">10.1016/j.neuron.2021.09.001</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EedZ-939p7BNtHrbnCRiVBIBWLbK0GNoCpz82i75JTVkWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq v4</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">Human Multiple Cortical Areas Smart-seq</td>
      <td name="td8"><a href="https://portal.brain-map.org/atlases-and-data/rnaseq/human-multiple-cortical-areas-Smart-seq" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_MultipleCorticalAreas_AllenBrain_2019_SMART-Seq</td>
      <td name="td11">https://portal.brain-map.org/atlases-and-data/rnaseq/human-multiple-cortical-areas-Smart-seq</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Efp2Bykmd2ZJlVyuK3mCsVMBomTyfGFag9Wjo5Uue6dcCg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Motor cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">Human M1 10x</td>
      <td name="td8"><a href="https://portal.brain-map.org/atlases-and-data/rnaseq/human-m1-10x" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_motor cortex_AllenBrain_2020_10x</td>
      <td name="td11">https://portal.brain-map.org/atlases-and-data/rnaseq/human-m1-10x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcsvAlQeDFpPnYhnUOCiQUsBW4poe7nN6lcP7jv3878OIw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Multiple sclerosis</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE179590</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE179590" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_PFC_Kihara_2022_10x</td>
      <td name="td11">10.3389/fncel.2022.918041</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeTUuvTatYpBnID0Vw7J5U4BMyiElENDKlafN9gvwCL7Ug?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE163018</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE163018" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_CorticalOrganoids_Ziffra_2021_ATAC-seq_10x</td>
      <td name="td11">10.1038/s41586-021-03209-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ebcm9U9qjfFMgAeK-Z8ALMEBHGo0xL4CRJBSY-jsS09AoA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Development</td>
      <td name="td4">Split-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://www.covid19cellatlas.org/aldinger20/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_FetalCerebellum_Aldinger_2021_SPLiT-seq</td>
      <td name="td11">10.1038/s41593-021-00872-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbdTl0fY39RIs8uYcv7oQfsBmBFphurBO3sroeNS3Qjr5A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Ganglionic eminences</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE165388</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE165388" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_fetal_Yu_2021_10x</td>
      <td name="td11">10.1038/s41593-021-00940-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfN7NwcT7BNMgJ-_OrBWoNkBlK2IC7ztt8HQvyYMxL6eeg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE157827</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE157827" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Lau_2020_10x</td>
      <td name="td11">10.1073/pnas.2008762117</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQh1RxpWkSNIkRz2RGW8I9sBaU2TPua2wb1rZx3QNKt6lQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Midbrain</td>
      <td name="td3">Parkinson's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE157783</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE157783" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_microglia_midbrain_Smajic_2022_10x</td>
      <td name="td11">10.1093/brain/awab446</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec6Wic5AcStLk2TSWiIvuc8B00hHb2e9qs73NAL_mzXofQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE129308</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE129308" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Otero-Garcia_2022_10x</td>
      <td name="td11">10.1016/j.neuron.2022.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eem_QymyuthKkv51knArGJYBYPMKJ9is_JQ9ECWb7Oi4hQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Brain</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE141862</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE141862" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Microglia_Kracht_2020_Smartseq2</td>
      <td name="td11">10.1126/science.aba5906</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbgkpXuCxqBMrO8Z_9_BvG4BMNgVPLilWI4aSi3d7km3AQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Spinal cord</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE141862</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE141862" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Microglia_Kracht_2020_Smartseq2</td>
      <td name="td11">10.1126/science.aba5906</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbgkpXuCxqBMrO8Z_9_BvG4BMNgVPLilWI4aSi3d7km3AQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Organoid growth</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE168323</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE168323" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_organoids_Fiorenzano_2021_10x</td>
      <td name="td11">10.1038/s41467-021-27464-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeIrmx-BbtNNrFZJU_pG7pgBZ9XyPfOGMSXAHWoEj_DY-A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Organoid growth</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE190815</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE190815" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_organoids_Revah_2022_10x</td>
      <td name="td11">10.1038/s41586-022-05277-w</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVPgGPdlZlNNgn3XUJrstiwB1kh7OOzWj2RCsaHRw9djJw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Major depressive disorder</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE144136</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144136" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Nagy_2020</td>
      <td name="td11">10.1038/s41593-020-0621-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ef0rbCIr_HRKqqKIkvk8r_cB4AgHYz7JFfgRruSpx7XrsQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE160189</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE160189" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Fatma_2020</td>
      <td name="td11">10.1016/j.neuron.2021.05.003</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESLPBZ3fSbVKqSQwHwfg488BBN0SY1fBXZNb6frpRTxAgw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE139448</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE139448" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_radialglia_WangR_2020_10x</td>
      <td name="td11">10.1016/j.stemcr.2020.01.007</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYOmYLIisaVAnFhqSnF2c58BcXMuphU_Visz3Xo-RZdktg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE167494</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE167494" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Sadick_2022_10x</td>
      <td name="td11">10.1016/j.neuron.2022.03.008</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ed1bzJKd8WlFqdsD3G3SFXwBdYpOOBYzsGf-y-CpGQhK2g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE97930</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE97930" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_FC_Cerebellum_Lake_2017_snDrop-Seq</td>
      <td name="td11">10.1038/nbt.4038</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaqL4JiVDjFNoA6KL5psz2oBt4Tdpjgjwe2e_twgIe7ySw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE97930</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE97930" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_FC_Cerebellum_Lake_2017_snDrop-Seq</td>
      <td name="td11">10.1038/nbt.4038</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaqL4JiVDjFNoA6KL5psz2oBt4Tdpjgjwe2e_twgIe7ySw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE131928</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE131928" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBM_Neftel_2019_Smartseq2_10x</td>
      <td name="td11">10.1016/j.cell.2019.06.024</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXeEaLNIb7RMkQAtivX-n9oB47JOlMwLM57GXec6PRFXKA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Microwell-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE103224</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE103224" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glioma_Yuan_2018_Microwell</td>
      <td name="td11">10.1186/s13073-018-0567-9</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcaBkr-XU1dDiqdbV8z78jcBSDIYzt6cxNAyiW0ov1ZXWQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE148822</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE148822" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_microglia_Gerrits_2021_10x</td>
      <td name="td11">10.1007/s00401-021-02263-w</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfqMXSpGD2tKnF2kGOBFFZ8BT58tG60xSJsvKP5GhyPYAA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Frontotemporal dementia</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE163122</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE163122" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Frontaltemporal_Gerrits_2022_10x</td>
      <td name="td11">10.1038/s41593-022-01124-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdNZEFqP781Et7njTcmHop8BgprcJMe91yViMerc3RKaAQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE89567</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE89567" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glial_Venteicher_Smartseq2</td>
      <td name="td11">10.1126/science.aai8478</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQhruc-3WYRFp09DT7ZhCasBOulkZmwr8KJ5Pr-zvQNLdw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">mCEL-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE135437</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE135437" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBM_Sankowski_2019_mCEL-seq2</td>
      <td name="td11">10.1038/s41593-019-0532-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EX-_3M57hN9PtGorT5FT2xsB8zYAvEF1yuq5QFsvKgZTZQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Entorhinal cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">DroNc-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE138852</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE138852" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_entorhinalcortex_Grubman_2019_DroNc-seq</td>
      <td name="td11">10.1038/s41593-019-0539-4</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EewY1spP86pNmq0LLCq8iE4BG3Gw0Cn-uL1P2zxzwjujaw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE147528</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE147528" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Leng_2021_10x</td>
      <td name="td11">10.1038/s41593-020-00764-7</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ed5CxZG267FKm04rFOQ0licBxQevbvFavV-yU6nqqouL0Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Microglia</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE146639</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE146639" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Alsema_2020_10x</td>
      <td name="td11">10.3389/fnmol.2020.00134</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaFtnYYzykVEnV7xB8Xt4e8Bgsa8tDd7yWDAv1lRms7EIg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Glioma</td>
      <td name="td4">Modified Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE144462</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144462" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glial_Fu_2021_PCR</td>
      <td name="td11">10.1016/j.celrep.2021.108788</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZ2gjwPWvitJrScwlEgYoRsB8FtRc7k8-qD2xkIBmGYMTw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Modified Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE144462</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE144462" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glial_Fu_2021_PCR</td>
      <td name="td11">10.1016/j.celrep.2021.108788</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZ2gjwPWvitJrScwlEgYoRsB8FtRc7k8-qD2xkIBmGYMTw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE103723</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE103723" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Fan_2018</td>
      <td name="td11">10.1038/s41422-018-0053-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EblBo04AMtNLtxCCeitsXb0BJ6OALFAH1AY0exR2hA0KEg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Basal ganglia</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE126836</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE126836" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_Welch_2019_10x</td>
      <td name="td11">10.1016/j.cell.2019.05.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeXBbR1P6tpHkiFz3OKOoNsBoscjFEGuZKeScMmvzNYvoA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Basal ganglia</td>
      <td name="td3">Parkinson's disease</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE178265</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE178265" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SNpc_Kamath_2022_10x_Slide</td>
      <td name="td11">10.1038/s41593-022-01061-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">DroNc-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE71585</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71585" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Habib_2017</td>
      <td name="td11">10.1038/nmeth.4407</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeiTbsbnvNRHrH1LiWt-CLIBnvF2Yo4hd0x7NUZRxGuoWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">DroNc-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE71585</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE71585" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Habib_2017</td>
      <td name="td11">10.1038/nmeth.4407</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeiTbsbnvNRHrH1LiWt-CLIBnvF2Yo4hd0x7NUZRxGuoWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE162170</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE162170" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Trevino_cortex_2021_10x</td>
      <td name="td11">10.1016/j.cell.2021.07.039</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EWjjLQqXaVlFk83gkUUtSy0BDr6Xeco7YoSHfOx7Gr0qsg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE131258</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE131258" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_hippocampus_Zhong_2019_ATAC-seq</td>
      <td name="td11">10.1038/s41586-019-1917-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eb4aG0eOg7BOrX-WHwlvCQsBxH49kWqgAoA5dLZ03Wal-g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="http://bit.ly/cortexSingleCell" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_RadialGlia_Nowakowski_2017_FluidigmC1</td>
      <td name="td11">10.1126/science.aap8809</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbZJed85DGxBkyIMixCvKagB73uyDu-saENJfXK0eFx4AQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE148842</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE148842" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_GBM_Zhao_2020_Microwell</td>
      <td name="td11">10.1186/s13073-021-00894-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETMkLHlhaG1DiAsUgTnKvMoB4rpyTB_sZA17hB6eIvqA-A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Brain vasculature</td>
      <td name="td3">Malform vasculature</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://cells.ucsc.edu/?ds=adult-brain-vasc" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_vascular_winkler_2022_10x</td>
      <td name="td11">10.1126/science.abi7377</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EflUSSLIuOdCjuIEAyt8q38B6cZvSURZORdNwnAT1XGvug?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE102130</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE102130" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_glioma_Filbin_2018_Smartseq2</td>
      <td name="td11">10.1126/science.aao4750</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ebge7AIbMhhBumorviBG1_cBIxB1mQBoYvDHd0b6iwaHDA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE84465</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE84465" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Glioblastoma_Darmanis_2017_SmartSeq2</td>
      <td name="td11">10.1016/j.celrep.2017.10.030</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ebo2RC467sdPv-IJqAzGx2ABU18V_1kSsnLztmUQfcqAQw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Tumour</td>
      <td name="td2">Tumour</td>
      <td name="td3">Glioma</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE70630</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE70630" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Oligodendrogliomas_Tirosh_2016_Smartseq2_STRT-seq</td>
      <td name="td11">10.1038/nature20123</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESy_HcatgWhPoOy8uGw8BSkBE9VgSPzAyHqmbfF73NuR1w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Organoid growth</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">E-MTAB-10974</td>
      <td name="td8"><a href="https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-10974" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_cerebral_organoids_He_2021_10x_Visium_iTracer_perturb</td>
      <td name="td11">10.1038/s41592-021-01344-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ea3SaLzaYyZAucwnbSI7544BA7BUgGZFe_vmTYRyNY6Aag?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Organoid growth</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">E-MTAB-12001</td>
      <td name="td8"><a href="https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-12001" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_cerebral_organoids_Fleck_2022_10x_ATAC</td>
      <td name="td11">10.1038/s41586-022-05279-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ea4nTDqTZjRHgUbMTzqtwh8B8hGu4tp5wbBIXmXEmv97Hg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">SCR_016152</td>
      <td name="td8"><a href="https://assets.nemoarchive.org/dat-37m82a9dat-zkgd0it" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_chimp_macaque_PFC_Ma_2022_ATAC-seq_10x</td>
      <td name="td11">10.1126/science.abo7257</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETQudBJHBOJPgEICp2fXlMUBGec5pctpkWKkv69_e0Z8nQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">E-MTAB-8230</td>
      <td name="td8"><a href="https://www.ebi.ac.uk/biostudies/arrayexpress/studies/E-MTAB-8230" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_chimpanzee_bonobo_macaque_brain_source_Kanton_2019</td>
      <td name="td11">10.1038/s41586-019-1654-9</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaZg-Sb2IuNDgtZJd6m6iJcB5akbtlSA47DrgGuVF4zCnA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">STRT-seq2</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE101601</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE101601" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_SomatosensoryCortex_Hochgarner_2017_STRT-seq</td>
      <td name="td11">10.1038/s41598-017-16546-4</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUVEcCQFnKFHh_rdGYvyEXkBgD-dpOMqC0ticK-sfB5eoA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cingulate cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">syn22213200</td>
      <td name="td8"><a href="https://www.synapse.org/#!Synapse:syn22213200" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_source_Gaublomme_2019</td>
      <td name="td11">10.1038/s41467-019-10756-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbPj7PAnoN5HlO8Em0gj5NMBjd27hMINdxXQskKZhEYXaQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="http://development.psychencode.org/#" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_frontoparietal_Li_2018</td>
      <td name="td11">10.1126/science.aat7615</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ4AyrP7JaJOqhUiSQMYr40BG_SToWsU39zVUCrajy5EGQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Fluidigm C1</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="http://development.psychencode.org/#" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_frontoparietal_Li_2018</td>
      <td name="td11">10.1126/science.aat7615</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ4AyrP7JaJOqhUiSQMYr40BG_SToWsU39zVUCrajy5EGQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE104276</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE104276" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_source_Zhong_2018</td>
      <td name="td11">10.1038/nature25980</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUW04vqVWfBAhSISPU2QlqgBlnX9VQja2iWujM0GlFeTGw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132672</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132672" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">brain_Bhaduri2020_Human_10x</td>
      <td name="td11">10.1038/s41586-020-1962-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/IQPFAHY4Gg6RSr-YEL1NbVQ-AQk6dh5ygGWThPiio_GgXH8?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Organoid growth</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132672</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132672" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">brain_Bhaduri2020_Human_10x</td>
      <td name="td11">10.1038/s41586-020-1962-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/IQPFAHY4Gg6RSr-YEL1NbVQ-AQk6dh5ygGWThPiio_GgXH8?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Organoid</td>
      <td name="td2">Organoid</td>
      <td name="td3">Healthy</td>
      <td name="td4">STICR</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE187875</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE187875" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_cerebralcortex_Delgato_2022</td>
      <td name="td11">10.1038/s41586-021-04230-7</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EePUkGdzmZpOj-LvjD3OIP4Bv1lTwX5NG0YFEoCaZTWN8A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Split-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE199243</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE199243" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Hippocampus_Su_2022_10x</td>
      <td name="td11">10.1016/j.stem.2022.09.010</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETWB0FihHERFlSBnemF0LwMBwm5OR2HxgBA9wJ7oqJiLfg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Split-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE185553</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE185553" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_hippocampus_YiZhou_2022_10x</td>
      <td name="td11">10.1038/s41586-022-04912-w</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ4H43SuXvxAqy7hoTF_gSMB6GAzt7YRoQxn3VdvNRyXMQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Split-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE185277</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE185277" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_hippocampus_YiZhou_2022_10x</td>
      <td name="td11">10.1038/s41586-022-04912-w</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ4H43SuXvxAqy7hoTF_gSMB6GAzt7YRoQxn3VdvNRyXMQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Split-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE198323</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE198323" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_hippocampus_YiZhou_2022_10x</td>
      <td name="td11">10.1038/s41586-022-04912-w</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ4H43SuXvxAqy7hoTF_gSMB6GAzt7YRoQxn3VdvNRyXMQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Pituitary gland</td>
      <td name="td3">Development</td>
      <td name="td4">Modified split-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE142653</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE142653" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Pituitary_gland_Zhang_2020_STRTseq</td>
      <td name="td11">10.1038/s41467-020-19012-4</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZG4P3zxmfdPtm8mUC6HqIkBQX2dFwGswbAbAq8in62S9g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Cerebral cortex</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE160936</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE160936" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_Smith_2022_10x</td>
      <td name="td11">10.1007/s00401-021-02372-6</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eb74MGRiHABBlPAQrmgjY2kBoC4R6QiuU0zGu1v8fRJpDg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://github.com/linnarsson-lab/developing-human-brain/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_fetal_Braun_2022_10x</td>
      <td name="td11">10.1101/2022.10.24.513487</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQzkqoswCzJEmGxmgUeIymQBJCQi6TBEj4GKxRFGLmCwrw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Thalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq v4</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE182211</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE182211" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_macque_brain_Bakken_2021_SMARTer</td>
      <td name="td11">10.7554/eLife.64875</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETh5ZeQ4SB5EibffCqr9gF4BuFcBnaysYnC9X9-d7eij-A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Adult</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE186538</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE186538" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_brain_hippocampus_Franjic_2021_10x</td>
      <td name="td11">10.1016/j.neuron.2021.10.036</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EV1I3cKRmg9FlcrmndUL23oBp-PCMCREVmq__4gpdMbk7A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE95315</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE95315" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_dentate_gyrus_Hochgerner_2018_10x_C1</td>
      <td name="td11">10.1038/s41593-017-0056-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQb7JHu-qNJOumkIDP8ee_oB3qn7w0vo8yUYU0a8LCGgmg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE104323</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE104323" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_dentate_gyrus_Hochgerner_2018_10x_C1</td>
      <td name="td11">10.1038/s41593-017-0056-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQb7JHu-qNJOumkIDP8ee_oB3qn7w0vo8yUYU0a8LCGgmg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Human</td>
      <td name="td1">Fetal</td>
      <td name="td2">Midbrain</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE76381</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE76381" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_midbrain_LaManno_2016_STRT-seq</td>
      <td name="td11">10.1016/j.cell.2016.09.027</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUoMzanbRR9BnHRWzLumSiMBiCTHGIqZMWhxT-cIXoxgIg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebullum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE165371</td>
      <td name="td8"><a href="https://www.nature.com/articles/s41586-021-03220-z#data-availability" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cerebullum_Kozareva_2021_10x</td>
      <td name="td11">10.1038/s41586-021-03220-z</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaFDPtKNidtEiKdS8fYLHhIBnDAOn3tdXcTtiVKzu9VkzA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Striatum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE149897</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE149897" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Striatum_Microglia_Badimon_2020_10x</td>
      <td name="td11">10.1038/s41586-020-2777-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXRBjzZcU0NIrhqomL7D1v0BPweCe2dnks4CXbaiy-Ta1g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE93421</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/data/public/SCP383" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortex_Zheng_2017_10x</td>
      <td name="td11">10.1038/ncomms14049</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EefKwyaw11xIqyoMiUJxW1sBKpwac9chAvveM_3I8brQnQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE93421</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/data/public/SCP383" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortex_Zheng_2017_10x</td>
      <td name="td11">10.1038/ncomms14049</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EefKwyaw11xIqyoMiUJxW1sBKpwac9chAvveM_3I8brQnQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Subventricular zone</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE93421</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/data/public/SCP383" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortex_Zheng_2017_10x</td>
      <td name="td11">10.1038/ncomms14049</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EefKwyaw11xIqyoMiUJxW1sBKpwac9chAvveM_3I8brQnQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">CTX-HPF</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://portal.brain-map.org/atlases-and-data/rnaseq/mouse-whole-cortex-and-hippocampus-10x" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CTX-HPF_AllenBrain_2020_10x</td>
      <td name="td11">10.1016/j.cell.2021.04.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXipmh9uTTpAhcuoHLVa1IgBPP-KviAgwnrLLkGA4wqkLw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Frontal cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Thalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Poster cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Striatum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Globus pallidus extermus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Entopeduncular nucleus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Substansia nigra</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE116470</td>
      <td name="td8"><a href="http://dropviz.org/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Saunders_2018_Drop-Seq</td>
      <td name="td11">10.1016/j.cell.2018.07.028</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUaG2YO5vFJIqxRo2SinN3YBuYiuM8nA4qPPv7pT_UzyUQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132355</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132355" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hypothalamus_Kim_2020_10x</td>
      <td name="td11">10.1038/s41467-020-18231-z</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EaGgd5O__WFJurfPfab1XugBBilWOzNIW3AtPxB4zyE4Bg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal raphe nucleus</td>
      <td name="td3">Rabies</td>
      <td name="td4">InDrops</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE136455</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE136455" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_dorsal_raphe_nucleus_Huang_2020_InDrops</td>
      <td name="td11">10.3389/fncel.2020.00065</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQ1jamlVLJtOtKBbe6D4pp0B-lBGhKPJbSf0JWBs7-XzEg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">Slide-seqV2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">SCP815</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/study/SCP815" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hippocampus_Stickels_2021_Slide_seqV2</td>
      <td name="td11">10.1038/s41587-020-0739-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYRYB8cdTYBOgslOuSSWaxwBkRnZLUdZwDo5rUYZvUsQOg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Embryo</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">PRJNA637987</td>
      <td name="td8"><a href="http://mousebrain.org/development/downloads.html" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_LaManno_2021_10x_HybISS</td>
      <td name="td11">10.1038/s41586-021-03775-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZMx9kKFoDNHn0Y-M66Weq4BxOyVf4uyjVzw2ndMM2x8MA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hindbrain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">PRJNA637987</td>
      <td name="td8"><a href="http://mousebrain.org/development/downloads.html" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_LaManno_2021_10x_HybISS</td>
      <td name="td11">10.1038/s41586-021-03775-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZMx9kKFoDNHn0Y-M66Weq4BxOyVf4uyjVzw2ndMM2x8MA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Midbrain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">PRJNA637987</td>
      <td name="td8"><a href="http://mousebrain.org/development/downloads.html" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_LaManno_2021_10x_HybISS</td>
      <td name="td11">10.1038/s41586-021-03775-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZMx9kKFoDNHn0Y-M66Weq4BxOyVf4uyjVzw2ndMM2x8MA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Forebrain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">PRJNA637987</td>
      <td name="td8"><a href="http://mousebrain.org/development/downloads.html" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_LaManno_2021_10x_HybISS</td>
      <td name="td11">10.1038/s41586-021-03775-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZMx9kKFoDNHn0Y-M66Weq4BxOyVf4uyjVzw2ndMM2x8MA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Medial Prefrontal Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE135326</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE135326" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Chu_2019_10x</td>
      <td name="td11">10.1038/s41586-019-1644-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeHAJy2zuuBAkgQfSFw-6OgBd77YgR8s3pppNX3ZcacRCQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">10.17632/ypx3sw2f7c.1</td>
      <td name="td8"><a href="https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/ypx3sw2f7c-1.zip" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_VMH_Kim_2019_10x_smart_seqFISH</td>
      <td name="td11">10.1016/j.cell.2019.09.020</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcDnWDTIzaVEuhf1LZVJz24BPpxcx1g389d7cosJ7wEgdQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">SMARTer</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">10.17632/ypx3sw2f7c.1</td>
      <td name="td8"><a href="https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/ypx3sw2f7c-1.zip" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_VMH_Kim_2019_10x_smart_seqFISH</td>
      <td name="td11">10.1016/j.cell.2019.09.020</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcDnWDTIzaVEuhf1LZVJz24BPpxcx1g389d7cosJ7wEgdQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">seqFISH</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">10.17632/ypx3sw2f7c.1</td>
      <td name="td8"><a href="https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/ypx3sw2f7c-1.zip" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_VMH_Kim_2019_10x_smart_seqFISH</td>
      <td name="td11">10.1016/j.cell.2019.09.020</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcDnWDTIzaVEuhf1LZVJz24BPpxcx1g389d7cosJ7wEgdQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Embryos</td>
      <td name="td3">Development</td>
      <td name="td4">Microwell-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE178217</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE178217" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Brain_Fei_2022_Microwell</td>
      <td name="td11">10.21203/rs.3.rs-1544600/v1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQYtGakFxEhNnuqorshP9E0Byg-S11ASJkh5NpSNn5uIJA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Development</td>
      <td name="td4">Microwell-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE176063</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE176063" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Brain_Fei_2022_Microwell</td>
      <td name="td11">10.21203/rs.3.rs-1544600/v1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQYtGakFxEhNnuqorshP9E0Byg-S11ASJkh5NpSNn5uIJA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Striatum</td>
      <td name="td3">Huntington's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE141856</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE141856" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Striatum_Wertz_2020_10x</td>
      <td name="td11">10.1016/j.neuron.2020.01.004</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbWYnOVFGAtJnFp17oMFfcMBQOvBdP2g6zvNB9zNQCdOig?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Amygdala</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal root ganglion</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal striatum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampal formation</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Medulla</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Midbrain</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Olfactory bulb</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Pons</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Spinal cord</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Sympathetic nervous system</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Temporal lobe</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Thalamic complex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Ventral striatum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">SRP135960</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/2c041c26-f75a-495f-ab36-a076f89d422a/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Amit_2018</td>
      <td name="td11">10.1016/j.cell.2018.06.021</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQjMwBuvw8NDlOP1crt9RWsBBwx9Y7xSufNPnf40_nhScw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Development</td>
      <td name="td4">Split-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE110823</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE110823" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_spinalcord_Rosenberg_2018_SPLiT-seq</td>
      <td name="td11">10.1126/science.aam8999</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETfmrhH43LBCsq7j3Q91tPAB6LZTx5URzkyxRcuHCS_TYw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Lateral geniculate nucleus (thalamus)</td>
      <td name="td3">Development</td>
      <td name="td4">InDrops</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE108761</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE108761" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_LGN_Kalish_2018_InDrops</td>
      <td name="td11">10.1073/pnas.1717871115</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcBz0cXJ2uRHtRd1HY7OproBX4R-O01gIJBTk2zPMu0FFg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Healthy</td>
      <td name="td4">EEL FISH</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://figshare.com/articles/dataset/EEL_Mouse_440_genes_single_cell_data/20310771?file=37550806" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Borm_2022_EEL_FISH</td>
      <td name="td11">10.1038/s41587-022-01455-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ERu-bSMXbmFPpXBF5UKQnvUB5Bj-DuAI0deBqI3GH41P3w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole Cortex</td>
      <td name="td3">Autism spectrum disorder</td>
      <td name="td4">Perturb-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE157977</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/study/SCP1184" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cortex_Jin_2020_Perturb</td>
      <td name="td11">10.1126/science.aaz6063</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdgvxLcKkYZEg3d6sxqvM9EB6pdyte0ilNTQgB9ATnsiCA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole Cortex</td>
      <td name="td3">Neurodevelopmental delay</td>
      <td name="td4">Perturb-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE157977</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/study/SCP1184" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cortex_Jin_2020_Perturb</td>
      <td name="td11">10.1126/science.aaz6063</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdgvxLcKkYZEg3d6sxqvM9EB6pdyte0ilNTQgB9ATnsiCA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Astrocyte</td>
      <td name="td3">Inflammation</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE148611</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE148611" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Astrocytes_Hasel_10x</td>
      <td name="td11">10.1038/s41593-021-00905-6</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVRql39uqEVKurtljycYh0UBfDuwPbAd9EOy14d2juKPkQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal root ganglia</td>
      <td name="td3">Spared nerve injury</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE155622</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE155622" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_DRG_Wang_2021_10x_smart</td>
      <td name="td11">10.1038/s41422-021-00479-9</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EddNWDlsgkVPvKjpSrA5Qz4BBhE4DS7gUpnTTDSF1GkoAg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal root ganglia</td>
      <td name="td3">Spared nerve injury</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE155622</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE155622" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_DRG_Wang_2021_10x_smart</td>
      <td name="td11">10.1038/s41422-021-00479-9</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EddNWDlsgkVPvKjpSrA5Qz4BBhE4DS7gUpnTTDSF1GkoAg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Auditory cortex A1</td>
      <td name="td3">Development</td>
      <td name="td4">InDrops</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE140883</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE140883" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_auditory_cortex_Kalish_2020_InDrops</td>
      <td name="td11">10.1073/pnas.1920433117</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EbnE9xRfxN9GlPaDMHl9XwcBhAgMeDDUWQMoQjlgY8ovjQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE121654</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE121654" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_microglia_Hammond_2018_10x</td>
      <td name="td11">10.1016/j.immuni.2018.11.004</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ET3jVPbQjx9MrYd116QcPcgBnFNXh9UQtr_IAEwp_TwkaQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">GABAergic neuron</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE188528</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE188528" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_GABAergicNeuron_Bandler_2021_10x</td>
      <td name="td11">10.1038/s41586-021-04237-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZ1jokNz8PRBixF9Wrh5VcwBOTI8g9cm_ZrAkKM-57Rjog?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Choroid plexus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE168704</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE168704" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_choroid_plexus_Dani_2021_10x</td>
      <td name="td11">10.1016/j.cell.2021.04.003</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EWs1oSKshHBBraUrVudR9-YBoM5s15lrlWtpin7-rkZyIg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Choroid plexus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE168704</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE168704" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_choroid_plexus_Dani_2021_10x</td>
      <td name="td11">10.1016/j.cell.2021.04.003</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EWs1oSKshHBBraUrVudR9-YBoM5s15lrlWtpin7-rkZyIg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Barrel cortex</td>
      <td name="td3">Whisker lesioning</td>
      <td name="td4">InDrops</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE129150</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE129150" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_barrel_somatosensory_cortex_Gunner_2019_InDrops</td>
      <td name="td11">10.1038/s41593-019-0419-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXOlphnXMyBMrtp8TwDJkbUBM3nKV1KbldG7DAOQDdjJfg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE143758</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE143758" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hippocampus_Habib_2020_10x</td>
      <td name="td11">10.1038/s41593-020-0624-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeiTbsbnvNRHrH1LiWt-CLIBnvF2Yo4hd0x7NUZRxGuoWg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Prenatal neocortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE140817</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE140817" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_NSCs_ZhangY_2020_10x</td>
      <td name="td11">10.1016/j.celrep.2020.03.027</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVvFkJAk8WFCqTKwgA-cPlMBMRzh4L3PbsKxXu4NOscyuA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Suprachiasmatic nucleus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE117295</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE117295" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_suprachiasmatic_nucleus_Wen_2020_10x_Drop_LCM</td>
      <td name="td11">10.1038/s41593-020-0586-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQChiU_a-ApKlnycEaUIPwwB5DHUke2DKq5k5PwEgQr_HA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Suprachiasmatic nucleus</td>
      <td name="td3">Healthy</td>
      <td name="td4">LCM-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE118403</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118403" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_suprachiasmatic_nucleus_Wen_2020_10x_Drop_LCM</td>
      <td name="td11">10.1038/s41593-020-0586-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQChiU_a-ApKlnycEaUIPwwB5DHUke2DKq5k5PwEgQr_HA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Suprachiasmatic nucleus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132608</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132608" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_suprachiasmatic_nucleus_Wen_2020_10x_Drop_LCM</td>
      <td name="td11">10.1038/s41593-020-0586-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQChiU_a-ApKlnycEaUIPwwB5DHUke2DKq5k5PwEgQr_HA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Brain metastasis</td>
      <td name="td4">CITE-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE134285</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE134285" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Guldner_2020_CITE</td>
      <td name="td11">10.1016/j.cell.2020.09.064</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ET9qo7-VzjRFm_35QZBj0EIBmM_0_z44KzyptYQh3Bbl7w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE128855</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE128855" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_VanHove_2019_10x</td>
      <td name="td11">10.1038/s41593-019-0393-4</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EW7KvRKaTntDuZOtYI5I6u4BbPabt4kFEF-79HueoHhTmw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Visual cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">InDrops</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE102827</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE102827" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_visual_cortex_Hrvatin_2017_InDrops</td>
      <td name="td11">10.1038/s41593-017-0029-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EcDnWDTIzaVEuhf1LZVJz24BPpxcx1g389d7cosJ7wEgdQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortical inhibitory interneurons</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE104158</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE104158" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortical_inhibitory_interneurons_Mayer_2018_10x_drop_smart</td>
      <td name="td11">10.1038/nature25999</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESo488CJJ_tGk0uOtEl7tqcBALYpwxTx5LCUneLtQ4x8ww?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortical inhibitory interneurons</td>
      <td name="td3">Development</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE104158</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE104158" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortical_inhibitory_interneurons_Mayer_2018_10x_drop_smart</td>
      <td name="td11">10.1038/nature25999</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESo488CJJ_tGk0uOtEl7tqcBALYpwxTx5LCUneLtQ4x8ww?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortical inhibitory interneurons</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE104158</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE104158" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortical_inhibitory_interneurons_Mayer_2018_10x_drop_smart</td>
      <td name="td11">10.1038/nature25999</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESo488CJJ_tGk0uOtEl7tqcBALYpwxTx5LCUneLtQ4x8ww?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Mesial cerebellum</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118068</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118068" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hindbrain_Vladoiu_2019_10x</td>
      <td name="td11">10.1038/s41586-019-1158-7</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVv87x5Ob4hFuVjQeKp1QUEBVjL6yvocMhjoB1YqdJwdlg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hindbrain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118068</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118068" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hindbrain_Vladoiu_2019_10x</td>
      <td name="td11">10.1038/s41586-019-1158-7</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVv87x5Ob4hFuVjQeKp1QUEBVjL6yvocMhjoB1YqdJwdlg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Ischemic stroke</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE174574</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE174574" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Zheng_2021_10x</td>
      <td name="td11">10.1177/0271678X211026770</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EclzicIL6kFBmgAim1K--BsB0Vjh-KxXeJBflbXu_qC5GQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Medial ganglionic eminence</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE165233</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE165233" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_interneuron_Allaway_2021_10x</td>
      <td name="td11">10.1038/s41586-021-03933-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQLXOJLFX4lJgAsK9xR9hYMB65J8YXe_xNuh2GJj-1he0w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE165233</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE165233" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_interneuron_Allaway_2021_10x</td>
      <td name="td11">10.1038/s41586-021-03933-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQLXOJLFX4lJgAsK9xR9hYMB65J8YXe_xNuh2GJj-1he0w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Interneurons</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE165233</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE165233" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_interneuron_Allaway_2021_10x</td>
      <td name="td11">10.1038/s41586-021-03933-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQLXOJLFX4lJgAsK9xR9hYMB65J8YXe_xNuh2GJj-1he0w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Olfactory bulb</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE121891</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE121891" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_OlfactoryBulb_Tepe_2018_10x</td>
      <td name="td11">10.1016/j.celrep.2018.11.034</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfKa8UDpyd1EigH7cwdWl0oBk-r7lEj1AB0f6OHOqtN2dg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132730</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132730" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hippothalamus_Romanov_2020_10x</td>
      <td name="td11">10.1038/s41586-020-2266-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZp_KKbx8WZHnmiHInX-B1IBoLqXg9n0GBMFU1JaDS89LQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE106678</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE106678" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortex_Hu_2017_sNucDrop</td>
      <td name="td11">10.1016/j.molcel.2017.11.017</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec1v4ILFK_xOtjNRh4OzKqEBJ09iFkLLmOHyYV8zVv2FkA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Nucleus accumbens</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE118020</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118020" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_ NAc_Chen_2021_10x</td>
      <td name="td11">10.1038/s41593-021-00938-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ERiWo6NnrixCmaTfmu11y78BkY7usfkPo0ndQWasV1UBiA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">sub-ventricular zone</td>
      <td name="td3">Healthy</td>
      <td name="td4">Microwell-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE109447</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE109447" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SubVentricularZone_Mizrak_2019_Microwell</td>
      <td name="td11">10.1016/j.celrep.2018.12.044</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYAsqFlHJVlJgmLioH0RLQEBo9OvtRV4SvvsNdWVUo37xA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE153164</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE153164" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cortex_DiBella_2021_10x_scATAC</td>
      <td name="td11">10.1038/s41586-021-03670-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EW7n7QIFLY9Mlyo66bK9DN8B-xlawmyD0lyvILkhU2OfSA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">hippocampus</td>
      <td name="td3">Epilepsy</td>
      <td name="td4">CITE-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE163480</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE163480" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Chung_2021_inCITE-seq</td>
      <td name="td11">10.1038/s41592-021-01278-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EV0UKl5rPzxMrub3Tbd-H3kBcQWSbTiWgMCP7ATefWliFw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">MARS-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE98969</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98969" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Keren-Shaul_2017_MARS</td>
      <td name="td11">10.1016/j.cell.2017.05.018</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZ2ifl8TqvtAkBY4QKZzuaIByC26s9ZtL2mTmMohCuy-Nw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">MARS-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE98969</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98969" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Keren-Shaul_2017_MARS</td>
      <td name="td11">10.1016/j.cell.2017.05.018</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZ2ifl8TqvtAkBY4QKZzuaIByC26s9ZtL2mTmMohCuy-Nw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE129788</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE129788" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_bran_microglia_Ximerakis_2019_10x</td>
      <td name="td11">10.1038/s41593-019-0491-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXF0mxbzA2RPoE4R3J30PPQBLYPmcHx5WdMaYMVGlFTDnQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Nucleus accumbens</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE118918</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118918" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_nucleus_accumbens_Avey_2018_drop</td>
      <td name="td11">10.1016/j.celrep.2018.08.080</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EccuGiaqIbtPrOwo9vKlRTQBXaN_ViVerJq4xzX6MiH8Kw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Human African trypanosomiasis (HAT)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE200642</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE200642" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_tumour_Quintana_2022_10x</td>
      <td name="td11">10.1038/s41467-022-33542-z</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfsioYic8sZAlo01xyOflk8BWAS7alT09nHPjUcEaMenhQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Forebrain</td>
      <td name="td3">Human African trypanosomiasis (HAT)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE200642</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE200642" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_tumour_Quintana_2022_10x</td>
      <td name="td11">10.1038/s41467-022-33542-z</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfsioYic8sZAlo01xyOflk8BWAS7alT09nHPjUcEaMenhQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Prefrontal cortical</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE124952</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE124952" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Bhattacherjee_2019</td>
      <td name="td11">10.1038/s41467-019-12054-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec5UDf0ubJNChwibH_wuxIYBuTN4Jc-aBAVNiwn1Vi2Ihg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dentate gyrus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE95753</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE95753" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_dentate_gyrus_Hochgerner_2018_10x_C1</td>
      <td name="td11">10.1038/s41593-017-0056-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQb7JHu-qNJOumkIDP8ee_oB3qn7w0vo8yUYU0a8LCGgmg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dentate gyrus</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE95753</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE95753" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_dentate_gyrus_Hochgerner_2018_10x_C1</td>
      <td name="td11">10.1038/s41593-017-0056-2</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQb7JHu-qNJOumkIDP8ee_oB3qn7w0vo8yUYU0a8LCGgmg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">preoptic region</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE113576</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE113576" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_preoptic_region_Moffitt_2018_10x</td>
      <td name="td11">10.1126/science.aau5324</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgF6iA-JaVDqD2I3Yw8-ocBy-tQDITbF-5kRtO1DnGTtw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE158450</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE158450" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_HPF_PFC_Joglekar_2021_10x_PacBio_Visium</td>
      <td name="td11">10.1038/s41467-020-20343-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESKCkpCbJu1IpuzX6JDFW0gBbNc2E3RWstkaUSiMsJaMYg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Prefrontal cortical</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE158450</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE158450" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_HPF_PFC_Joglekar_2021_10x_PacBio_Visium</td>
      <td name="td11">10.1038/s41467-020-20343-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESKCkpCbJu1IpuzX6JDFW0gBbNc2E3RWstkaUSiMsJaMYg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">lateral hypothalamic area</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130597</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE130597" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hypothalamus_Rossi_2019_Drop-Seq</td>
      <td name="td11">10.1126/science.aax1184</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EW25qxpd_jhFkDl-jTw7Vk0B3MVtjrwLYVv-1qRDNcRP_w?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">SMARTer</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE115746</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE115746" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_cortex_Tasic_2019_SMARTer</td>
      <td name="td11">10.1038/s41586-018-0654-5</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ea_Ad2mPaldOqXhK5fKp1lABsDPqondkKCv2KiFf_XhgEQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Inflammation</td>
      <td name="td4">Smart-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE164401</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE164401" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hippocampus_Miguel_2021_10x</td>
      <td name="td11">10.1038/s41586-021-04183-x</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZXXwRFcZbpOjg8VLMyUSBcBcrE9fT60kWZw9rZ48kbivg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Subventricular Zone</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE111527</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE111527" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SubventricularZone_Zywitza_2018_Drop-seq</td>
      <td name="td11">10.1016/j.celrep.2018.11.003</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeNU9NaPzHxNpIMrCPVFIRkBmfvw5F90r9ImgyBcMEYD9g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Osmosensory</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE154048</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE154048" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_osmosensory_Pool_2020_10x</td>
      <td name="td11">10.1038/s41586-020-2821-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVbWlCWjmYpKk9WtLvD5BmAByampEb7eEEKqdOlRg-Nmzg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neocortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE147247</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE147247" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_neocortex_Wittmann_2021_10x</td>
      <td name="td11">10.1242/dev.196022</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETXCYYimLOtElvBQ0Ed6VUMBDKWf_AfGpwcweh-Uile-jg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE122357</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE122357" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cerebellum_Peng_2018_10x</td>
      <td name="td11">10.1093/jmcb/mjy089</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eeg_XkkrnAhGtmOw8LwonscBrPZvpruI1P0v0TQMbrOuDg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamic arcuate-median eminance complex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE93374</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE93374" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Arcuate_Nucleus_Median_Eminence_Campbell_2017_drop</td>
      <td name="td11">10.1038/nn.4495</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EeWLgiEkxDJCh_QljU4s74QBXKbwSiIY2kgm0Agpv2D7UA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Medial amygdala</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE103976</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE103946" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Amygdala_Wu_2017_Drop-seq</td>
      <td name="td11">10.1016/j.neuron.2017.09.026</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec5PzHjyT6ZMurkc-8dpmcQB_zP76pkSQxifhV5PUZkjbg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Alzheimer's disease(gene model)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE142267</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE142267" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Microglia_Sierksma_2022_10x</td>
      <td name="td11">10.15252/emmm.201910606</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ET3jVPbQjx9MrYd116QcPcgBnFNXh9UQtr_IAEwp_TwkaQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neocortex</td>
      <td name="td3">Development</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE123335</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE123335" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_neocortex_Loo_2019_drop</td>
      <td name="td11">10.1038/s41467-018-08079-9</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUuZfq0-B05IpcvwozxP7a0BJH-XEnzkPP6RMnN5jdvn1A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Spinal cords</td>
      <td name="td3">Paralysis</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE142245</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE142245" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SpinalCords_Skinnider_2021_10x</td>
      <td name="td11">10.1038/s41587-020-0605-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZmiTos0SZdMqbSO9meuzbwBXReKirnke8Kpje8H2mAgHg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Autism spectrum disorder(gene model)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE146298</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE146298" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Fazel_2022</td>
      <td name="td11">10.1016/j.celrep.2020.03.059</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfcueTPXUyRIrLkEvqZzINUB_-T7YDBXXj3Q12xS8Evvhg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">L5 prefrontal neurons</td>
      <td name="td3">Autism spectrum disorder(gene model)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE146298</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE146298" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Fazel_2022</td>
      <td name="td11">10.1016/j.celrep.2020.03.059</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfcueTPXUyRIrLkEvqZzINUB_-T7YDBXXj3Q12xS8Evvhg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development(gene model)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE180345</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE180345" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hippocampal_Mirabella_2021_10x</td>
      <td name="td11">10.1016/j.immuni.2021.10.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EROXRgnEx8VGva-YWNN2h1cBp6RvtRT0qTYA1NdZRzeNbQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE132044</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE132044" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Ding_10x</td>
      <td name="td11">10.1038/s41587-020-0465-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EftrtK_Tzc9It4Jj-jmHMC4BI5qHwaBL7X64DUEEQ956og?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE87544</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE87544" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hypothalamus_Chen_2017_drop</td>
      <td name="td11">10.1016/j.celrep.2017.03.004</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVfqUE1AcidJu8RNLLWXreoBHnbxXb9QdJgzicQWjnvjQQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE178957</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE178957" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_developing_ZhangX_2022_10x</td>
      <td name="td11">10.1038/s41467-022-33226-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYdTveZpCxJMr_cBxJcSFzABc4min5ams4ShfuosKp-5mA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Healthy(Antibiotics-treated)</td>
      <td name="td4">CITE-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE148127</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE148127" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Golomb_2020_CITE</td>
      <td name="td11">10.1016/j.celrep.2020.108438</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUU-kSUqB3dEpz4QPDb_ZyEBJB8NYkqG1YOIDG_WIXC-9Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Nucleus accumbens</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE160486</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE160486" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_nucleus_accumbens_Kim_2020_10x</td>
      <td name="td11">10.1016/j.cell.2020.11.015</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ES_s-msbaq5NoDFnlbHEu2gB9XrwXXgz7iZAsfdNT6NG8Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Olfactory bulb</td>
      <td name="td3">Healthy</td>
      <td name="td4">SCOPE-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE134918</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE134918" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_OB_Mizrak_2020_SCOPE-seq</td>
      <td name="td11">10.1016/j.celrep.2020.107805</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZoUA2Ur0QxAvSIhVHzPBhUBGJnvO7P5CagX7scV3kfacg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE120372</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE120372" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cerebellum_Wizeman_2019_10x</td>
      <td name="td11">10.7554/eLife.42388</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ede5FlCQ2cBHjIleM5Tc7JQBKFBJdU-sI8EqKi9QYQ9aYg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Mild traumatic brain injury</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE101901</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE101901" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hippocampus_Arneson_2018_drop</td>
      <td name="td11">10.1038/s41467-018-06222-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYMAmBXZf29GkfWn_md7W7kB4krhNueD6CNWUkxUD0aZfg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Prefrontal cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE161936</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE161936" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Lui_2020_10x</td>
      <td name="td11">10.1016/j.cell.2020.11.046</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdJzEBZbEoxGg9LOagv3OboBVUH6r6kOaL5Io-CYZ-a4mw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Diencaphelon</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE122012</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE122012" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_diencephalon_Guo_2019_10x</td>
      <td name="td11">10.1242/dev.174284</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ee0YQfzf_OdMp1d3fsjVw-QBUrjrWBPvA6Mq2uEtyZDACg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Lateral hypothalamic area</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE125065</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE125065" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_lateral_hypothalamic_area_Mickelsen_2019_10x</td>
      <td name="td11">10.1038/s41593-019-0349-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EV8ZXFMylaBDvDPfoYA0WKMBO6rVyZDEDB-ts7xZ1ypqLg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">peripheral inflammation(gene model)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE145708</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE145708" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Cortex_S眉脽_2020_10x</td>
      <td name="td11">10.1016/j.celrep.2020.02.109</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamic arcuate nucleus</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE126480</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE126480" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_hypothalamic_Huisman_2019_10x</td>
      <td name="td11">10.1038/s41467-019-11667-y</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EQEBM3Z1cflCniWGVKsIym0BVFCYiT_VKurv7B7ZxqA-Nw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Embryonic cortex</td>
      <td name="td3">Development</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE107122</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE107122" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_EmbryonicCortex_Yuzwa_2017_Drop-Seq</td>
      <td name="td11">10.1016/j.celrep.2017.12.017</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYJ5yEVzjzhNsLJOz1DeW1sBWBKz-ApJGvemLknk5YRAZg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">CAMs</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">DCs</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Granulocytes</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Lymphocytes</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Monocyte-derived</td>
      <td name="td3">MOG35-55鈥搃mmunized</td>
      <td name="td4">CEL-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118948</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118948" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CD45_cells_Jord茫o_2019_mCEL</td>
      <td name="td11">10.1126/science.aat7554</td>
      <td name="td12"><a href="nan" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neocortex</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE143949</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE143939" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_forebrain_Li_2020_10x</td>
      <td name="td11">10.1126/sciadv.abd2068</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EXcHctRMVrZFr6eLNVehfrsBht1pwiG_5s5Fh8AZUeYwvQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Somatosensory cortex</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Striatum</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dentate gyrus</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Corpus collosum</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Amygdala</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hypothalamus</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Zona incerta</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Spinal cord</td>
      <td name="td3">Development</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2016</td>
      <td name="td7">GSE75330</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE75330" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_oligodendrocyte_Marques_2016_STRT</td>
      <td name="td11">10.1126/science.aaf6463</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfgvXXkdoj9CktdaY_qr2cMBG71McAvj30sbKZ1SNgVxOA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">infected with West Nile virus (WNV)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE212199</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE212199" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CortexHPF_Rosen_2022_10x</td>
      <td name="td11">10.1186/s13073-022-01111-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ERlBCsknqdhNtl7n3pKh9soBbgYQVsWEYVqK3w-BhiUQqQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">infected with West Nile virus (WNV)</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2022</td>
      <td name="td7">GSE212199</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE212199" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_CortexHPF_Rosen_2022_10x</td>
      <td name="td11">10.1186/s13073-022-01111-0</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ERlBCsknqdhNtl7n3pKh9soBbgYQVsWEYVqK3w-BhiUQqQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Forebrain</td>
      <td name="td3">Development(single or pairwise deletions of ultraconserved enhancers)</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE100394</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE100394" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_forebrain_Dickel_2018_drop</td>
      <td name="td11">10.1016/j.cell.2017.12.017</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdfLeUAV9r5Bs_6yqma4be0BfMMf_flHHAveV6pFTn3GDg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Ventricular subventricular zone</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE115600</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE115600" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SVZ_Kalamakis_2019_10x_smart</td>
      <td name="td11">10.1016/j.cell.2019.01.040</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYITbFi5qSdEts6N7okBDREBxYw82vcoPQd1dIinUYLLHA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Ventricular subventricular zone</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE115622</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE115622" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_SVZ_Kalamakis_2019_10x_smart</td>
      <td name="td11">10.1016/j.cell.2019.01.040</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYITbFi5qSdEts6N7okBDREBxYw82vcoPQd1dIinUYLLHA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cerebellum</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE98816</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE98816" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_vascular_Vanlandewijck_2018_Smart-seq2</td>
      <td name="td11">10.1038/nature25739</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EfdN78ubrg5JsGOalKgV91wBlhWqUUllk3ZgqOrnvZdFeA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Basal ganglia</td>
      <td name="td3">Healthy</td>
      <td name="td4">Drop-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2017</td>
      <td name="td7">GSE95133</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE95133" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_BasalGanglia_Wallace_2017_Drop-seq</td>
      <td name="td11">10.1016/j.neuron.2017.03.017</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Eehqz7bCWadOsXr8g1d18vwBlCbIiEQFuSMInhPLB2dp0g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neocortex</td>
      <td name="td3">Development</td>
      <td name="td4">SMARTer</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE118953</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE118953" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_ Neocortex_Telly_2019_SMARTer</td>
      <td name="td11">10.1126/science.aav2522</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ES5Iv6IXvU9Im3xewSi5HMgBUcPLHGrbRAP12FMfCAy3IA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Caudal ganglionic eminence</td>
      <td name="td3">Development</td>
      <td name="td4">SMARTer</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE109796</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE109796" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Mi_2018_SMARTer</td>
      <td name="td11">10.1126/science.aar6821</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ed_G_azel8RKlanwf4O9BO0B6m3EeLWAYqbVb9HPyd63eA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Dorsal and ventral medial ganglionic eminence</td>
      <td name="td3">Development</td>
      <td name="td4">SMARTer</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2018</td>
      <td name="td7">GSE109796</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE109796" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Mi_2018_SMARTer</td>
      <td name="td11">10.1126/science.aar6821</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ed_G_azel8RKlanwf4O9BO0B6m3EeLWAYqbVb9HPyd63eA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE123022</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE123022" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_mycroglia_myeloid_Li_2018_smart</td>
      <td name="td11">10.1016/j.neuron.2018.12.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVAEw6mO9H1IgV1pjjw8oyEBvOQee0_Cqn0sPS8fX0JX4Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE123024</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE123024" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_mycroglia_myeloid_Li_2018_smart</td>
      <td name="td11">10.1016/j.neuron.2018.12.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVAEw6mO9H1IgV1pjjw8oyEBvOQee0_Cqn0sPS8fX0JX4Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Microglia</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE123025</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE123025" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_mycroglia_myeloid_Li_2018_smart</td>
      <td name="td11">10.1016/j.neuron.2018.12.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVAEw6mO9H1IgV1pjjw8oyEBvOQee0_Cqn0sPS8fX0JX4Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Myeloid</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE123025</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE123025" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_mycroglia_myeloid_Li_2018_smart</td>
      <td name="td11">10.1016/j.neuron.2018.12.006</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EVAEw6mO9H1IgV1pjjw8oyEBvOQee0_Cqn0sPS8fX0JX4Q?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Astrocyte</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE114000</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE114000" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Astrocytes_Batiuk_2020_smart</td>
      <td name="td11">10.1038/s41467-019-14198-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ETrCI3lHG5tBiMnrQw7FUPIBeRWa4UkKv1wjWYZ-qFrUoQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Whole brain</td>
      <td name="td3">Development</td>
      <td name="td4">Chromium</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE138903</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE138903" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Ikonomou_2020_10x</td>
      <td name="td11">10.1038/s41467-020-14348-3</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EadTqOZOV4RHraM3QfK8Kq0ByUjjaKy-0LbCDQxMb9gwww?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">ScNaUmi-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130708</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/0d4b87ea-6e9e-4569-82e4-1343e0e3259f/m/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Kevin_2020</td>
      <td name="td11">10.1038/s41467-020-17800-6</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec3iYvyog1hFr1pfZcgOa_UBmNZ-MIIVlVTZqC_n3GyiVg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Cortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">ScNaUmi-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130708</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/0d4b87ea-6e9e-4569-82e4-1343e0e3259f/m/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Kevin_2020</td>
      <td name="td11">10.1038/s41467-020-17800-6</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec3iYvyog1hFr1pfZcgOa_UBmNZ-MIIVlVTZqC_n3GyiVg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Ventricular zone</td>
      <td name="td3">Healthy</td>
      <td name="td4">ScNaUmi-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE130708</td>
      <td name="td8"><a href="https://data.humancellatlas.org/explore/projects/0d4b87ea-6e9e-4569-82e4-1343e0e3259f/m/project-matrices" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_source_Kevin_2020</td>
      <td name="td11">10.1038/s41467-020-17800-6</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/Ec3iYvyog1hFr1pfZcgOa_UBmNZ-MIIVlVTZqC_n3GyiVg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Central Amygdala</td>
      <td name="td3">Healthy</td>
      <td name="td4">Chromium</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2023</td>
      <td name="td7">GSE231790</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE231790" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Amygdala_Peters_2022_mFISH</td>
      <td name="td11">10.1126/sciadv.adf6521</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EUXeQ6W5NaFDhhIe0wWcRJoBjFIoCiD-7O4qzK9DLF7Z8g?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Healthy</td>
      <td name="td4">Slide-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">SCP354</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/study/SCP354/slide-seq-study#/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Rodriques_2019_Slide-seq</td>
      <td name="td11">10.1126/science.aaw1219</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESbDt4x9bDtInS8OIh2eEpUB-0cyQXpiDEEjXmCfWg3EUg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Olfactory bulb</td>
      <td name="td3">Healthy</td>
      <td name="td4">Slide-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">SCP354</td>
      <td name="td8"><a href="https://singlecell.broadinstitute.org/single_cell/study/SCP354/slide-seq-study#/" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Rodriques_2019_Slide-seq</td>
      <td name="td11">10.1126/science.aaw1219</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/ESbDt4x9bDtInS8OIh2eEpUB-0cyQXpiDEEjXmCfWg3EUg?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neocortex</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">nan</td>
      <td name="td8"><a href="https://portal.brain-map.org/explore/classes/multimodal-characterization" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">human_mouse_brain_neocortex_Berg_2021_SMART-Seq</td>
      <td name="td11">10.1038/s41586-021-03813-8</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EYpq3KMmNfZLsED2QDc1I3wBHm0T3hGIhSvxCGcQAf50bQ?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neurons</td>
      <td name="td3">Healthy</td>
      <td name="td4">Smart-seq</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2021</td>
      <td name="td7">GSE181363</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE181363" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_neurons_Peng_2021_SMART-seq</td>
      <td name="td11">10.1038/s41586-021-03941-1</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EWAkAbbhjopKsm7deefw8XEBab34k22dElFgk1nq9SSegA?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
            
   
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Neural crest</td>
      <td name="td3">Development</td>
      <td name="td4">Smart-seq2</td>
      <td name="td5">scRNA-seq</td>
      <td name="td6">2019</td>
      <td name="td7">GSE129114</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE129114" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_NeuralCrest_Soldatov_2019_Smart-seq2</td>
      <td name="td11">10.1126/science.aas9536</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EdmDF5pONnZAshhWPL6hsBwBSkM4R_I3NBMNiNd5lfomJw?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   
  
     <tr>
      <td name="td0">Mouse</td>
      <td name="td1">Mouse</td>
      <td name="td2">Hippocampus</td>
      <td name="td3">Alzheimer's disease</td>
      <td name="td4">STRT-seq</td>
      <td name="td5">snRNA-seq</td>
      <td name="td6">2020</td>
      <td name="td7">GSE141044</td>
      <td name="td8"><a href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE141044" target="_blank" style="color:#23265F"><b>Link</b></a></td>
      <td name="td10">mouse_brain_Hippocampus_ZhongS_2020_STRT-Seq</td>
      <td name="td11">10.1080/09168451.2020.1714420</td>
      <td name="td12"><a href="https://1drv.ms/u/c/7b024e3a3857ddc3/EZS9-wY0g7tNoNWSCmovYPoBCmxDPtSYAAmht2jW6Rfn_A?download=1" target="_blank" style="color:#23265F"><b>Raw&Processed Data</b></a></td>
    </tr>
   </tbody>
</table>
</div>                
<script>
  var tables = [];
    var currentSheet = 'sheet1';
     $(document).ready(function() {
    $.noConflict();
    tables.push($('#cfttable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));

    tables.push($('#rnadetable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));

    tables.push($('#rnapretable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#smtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#eletable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));


    
    tables.push($('#amintable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#sugtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#tboxtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    tables.push($('#othtable').DataTable({
      dom: 'Bfrtip',
      buttons: [
        'copy', 'csv', 'excel', 'pdf', 'print'
      ]
    }));
    
    
    // Hide the search box for DataTables
      $('#cfttable_filter').css('display', 'none');
      $('#rnadetable_filter').css('display', 'none');
      $('#rnapretable_filter').css('display', 'none');
       $('#smtable_filter').css('display', 'none');
      $('#eletable_filter').css('display', 'none');
      $('#amintable_filter').css('display', 'none');
      $('#sugtable_filter').css('display', 'none');
      $('#tboxtable_filter').css('display', 'none');
      $('#othtable_filter').css('display', 'none');
      
      // Show the initial sheet (sheet1) and hide others
    showSheet('sheet1');
    hideAllSheetsExcept('sheet1');
  });

  function sortTable(columnIndex) {
    // TODO: Add sorting logic based on the columnIndex
  }

  

function downloadExcel() {
  var selectElement = document.getElementById('downloadOptions');
  var selectedValue = selectElement.value;

  // Check if a valid option was selected
  if (selectedValue !== '') {
    // Create a temporary link element with the download URL
    var link = document.createElement('a');
    link.href = selectedValue;
    link.download = selectedValue.split('/').pop(); // Set the filename to the last part of the URL
    document.body.appendChild(link);

    // Trigger a click event on the link to start the download
    link.click();

    // Remove the link from the DOM
    document.body.removeChild(link);
  }
}
	
	
	function showSheet(sheetId) {
    // Hide the current sheet
    if (currentSheet) {
        var currentSheetElement = document.getElementById(currentSheet);
        currentSheetElement.style.display = 'none';
    }

    // Show the selected sheet
    var sheet = document.getElementById(sheetId);
    sheet.style.display = 'block';

    // Update the current sheet
    currentSheet = sheetId;

    // Get all buttons
    var buttons = document.querySelectorAll('.button');

    // Remove clicked class from all buttons
    buttons.forEach(function(btn) {
        btn.classList.remove('clicked');
    });

    // Add clicked class to the clicked button using event.target
    event.target.classList.add('clicked');
}

  function hideAllSheetsExcept(sheetId) {
    var sheets = document.getElementsByClassName('sheet');
    for (var i = 0; i < sheets.length; i++) {
      var sheet = sheets[i];
      if (sheet.id !== sheetId) {
        sheet.style.display = 'none';
      }
    }
    }

    function showAllSheets() {
      var sheets = document.getElementsByClassName('sheet');
      for (var i = 0; i < sheets.length; i++) {
        sheets[i].style.display = 'block';
      }
    }

    function searchTables() {
      var keyword = $('#searchBox').val().toLowerCase();

      tables.forEach(function(table) {
        table.search(keyword).draw();
      });
      // Filter the sheets based on search results
    filterSheets();
  }

  function filterSheets() {
    var keyword = $('#searchBox').val().toLowerCase();
    var sheets = document.getElementsByClassName('sheet');

    for (var i = 0; i < sheets.length; i++) {
      var sheet = sheets[i];
      var table = tables[i];

      var displaySheet = false;

      table.rows().eq(0).each(function(index) {
        var row = table.row(index);
        var rowData = row.data().join(' ').toLowerCase();
        var display = rowData.includes(keyword) ? '' : 'none';
        row.nodes().to$().css('display', display);

        if (display !== 'none') {
          displaySheet = true;
        }
      });

      if (displaySheet) {
        $('#' + sheet.id).show();
      } else {
        $('#' + sheet.id).hide();
      }
    }
  }  
  </script>      