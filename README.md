<!doctype html>

<html>

<head>

<meta charset="utf-8">

<title>Tarih Hesapla</title>

<link rel="stylesheet" href="https://code.jquery.com/ui/1.12.0/themes/base/jquery-ui.css">

<script src="https://code.jquery.com/jquery-1.12.4.js"></script>

<script src="https://code.jquery.com/ui/1.12.0/jquery-ui.js"></script>

<p>Baslangic Tarihi : <input type="text" id="startdate"></p>
<p>Bitis Tarihi : <input type="text" id="enddate"></p>
<p>Gun Sayisi : <input type="text" id="days"></p>


<script>
$(document).ready(function() {

$( "#startdate,#enddate" ).datepicker({
changeMonth: true,
changeYear: true,
firstDay: 1,
monthNamesShort: [ "Ocak", "Şubat", "Mart", "Nisan", "Mayıs", "Haziran", "Temmuz", "Ağustos", "Eylül", "Ekim", "Kasım", "Aralık" ],
dayNamesMin: [ "Pa", "Pt", "Sa", "Ça", "Pe", "Cu", "Ct" ],
dateFormat: "dd.mm.yy"
})

$( "#startdate" ).datepicker({ dateFormat: 'dd-mm-yy' });
$( "#enddate" ).datepicker({ dateFormat: 'dd-mm-yy' });

$('#enddate').change(function() {
var start = $('#startdate').datepicker('getDate');
var end   = $('#enddate').datepicker('getDate');

if (start<end) {
var days   = (end - start)/1000/60/60/24;
$('#days').val(days);
}
}); //end change function

$("#startdate").change(function() {
var start = $('#startdate').datepicker('getDate');
var end   = $('#enddate').datepicker('getDate');

if (start<end) {
var days   = (end - start)/1000/60/60/24;
$('#days').val(days);
}
}); //end change function

}); //end ready
</script>
