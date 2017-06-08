# Countdown.github.io
Test for boss countdown


<aside id="sidebar">
<p style="font-size:16px;font-weight:bold;color:#FF7256;">网站访问次数：<label id="lb_count">0</label></p>
<button type="button" id="setOT">getOriginalTime</button>
<p style="font-size:16px;font-weight:bold;color:#FF7256;">原始时间：<label id="OT">0</label> 更新：<label id="OT_freshTime">0</label>次</p>
</aside>

<script src="https://apps.bdimg.com/libs/jquery/1.10.2/jquery.min.js"></script>
<script type="text/javascript">
$(function(){
//	getTotalPV();
	$("#setOT").click(function(){
			getOriginalTime();
		});
	});
	
	function getOriginalTime()
	{
	$.ajax({
			url:"https://cloud.bmob.cn/0cabcec239a03e45/getOriginalTime",
			dataType:'jsonp',
			data:'',
			jsonp:'callback',
			success:function(result) {
				$('#OT').html(result.results[0].updatedAt);
				$('#OT_freshTime').html(result.results[0].totalPV);
			}
		});
	}
	
	function getTotalPV()
	{
	$.ajax({
			url:"https://cloud.bmob.cn/0cabcec239a03e45/getTotalPV",
			dataType:'jsonp',
			data:'',
			jsonp:'callback',
			success:function(result) {
		           //result.results[0].totalPV
			   $('#lb_count').html(result.results[0].totalPV);
			   //更新次数
			   setTotalPV();
			}
		});
	}
	
	function setTotalPV()
	{
	$.ajax({
			url:"https://cloud.bmob.cn/0cabcec239a03e45/setTotalPV",
			dataType:'jsonp',
			data:'',
			jsonp:'callback',
			success:function(result) {
			}
		});
	}
</script>
