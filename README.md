<html>
<style>
.tab-content .content li {list-style: none;display: none;}
.tab-indent .tabs li {list-style: none;width: auto;display: inline-block;padding: 5px 10px;cursor: pointer}
.tab-indent .tabs li.opened{font-weight: bold; border-bottom: 1px solid;}
</style>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.1.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
	$(".tab-indent .tabs li").on("click", function(){
		$(".tab-indent .tabs li.opened").removeClass("opened");
		var index = $(this).addClass("opened").attr("id");
		if($(".tab-content .content li.active").length){
			$(".tab-content .content li.active").fadeOut(function(){				
				$(".active").removeClass("active");
				$(".tab-content .content li[data-rel='"+index+"']").addClass("active").fadeIn();
			});	
		}else{
			$(".tab-content .content li[data-rel='"+index+"']").addClass("active").fadeIn();
		}			
		return false;
	});
	$(".tab-indent .tabs li:eq(0)").trigger("click");
});
</script>
<body>
<div class="tab-indent">
	<ul class="tabs">
		<li id="tab1">Tab 1</li>
		<li id="tab2">Tab 2</li>
		<li id="tab3">Tab 3</li>
		<li id="tab4">Tab 4</li>
	</ul>
</div>
<div class="tab-content">
	<ul class="content">
		<li data-rel="tab1">
			<div>
				<h3>Tab Content 1</h3>
				<p>Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.</p>
			</div>
		</li>
		<li data-rel="tab2">
			<div>
				<h3>Tab Content 2</h3>
				<p>Contrary to popular belief, Lorem Ipsum is not simply random text. It has roots in a piece of classical Latin literature from 45 BC, making it over 2000 years old. </p>
			</div>
		</li>
		<li data-rel="tab3">
			<div>
				<h3>Tab Content 3</h3>
				<p>It is a long established fact that a reader will be distracted by the readable content of a page when looking at its layout. </p>
			</div>
		</li>
		<li data-rel="tab4">
			<div>
				<h3>Tab Content 4</h3>
				<p>The standard chunk of Lorem Ipsum used since the 1500s is reproduced below for those interested.</p>
			</div>
		</li>		
	</ul>
</div>
</body>
</html>
