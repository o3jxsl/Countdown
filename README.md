# Countdown.github.io
Test for boss countdown


<aside id="sidebar">
<p style="font-size:16px;font-weight:bold;color:#FF7256;">网站访问次数：<label id="lb_count">0</label></p>
</aside>

<!--<script src="jquery.js" type="text/javascript"></script>-->
<script src="https://apps.bdimg.com/libs/jquery/1.10.2/jquery.min.js"></script>
<script type="text/javascript">
      $(function(){
	   getTotalPV();
	});
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
