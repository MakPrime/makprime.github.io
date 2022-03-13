$(document).ready(function(){
	//Lang
	activeLang = 0;
	$(".langs").click(function(){
		if(activeLang == 0){
			$(".lang_b").addClass("height_show");
			activeLang = 1;
		} else {
			$(".lang_b").removeClass("height_show");
			activeLang = 0;
		}
	});
	$(".langs").hover(
		function(){
			$(".lang_b").addClass("height_show");
			activeLang = 1;
		},
		function(){
			$(".lang_b").removeClass("height_show");
			activeLang = 0;
		}
	);
	
	$("#mixer_begin").click(function(){
		$("#mixer_step1").hide();
		$("#mixer_step2").slideToggle(400);
	});
	
	//Count int
	$(document).on("click", ".b_minus", function(){
		count = parseFloat($(this).parent().siblings(".int").val());
		symbol = $(this).parent().siblings(".int").data("symbol");
		step = $(this).parent().siblings(".int").data("step");
		if(symbol == "" || symbol == undefined){
			symbol = "";
		}
		if(step == "" || step == undefined){
			step = 1;
		}
		if(count > 0){
			count = count - step;
				if(count == 0){
					count = 0;
				}
			$(this).parent().siblings(".int").val(count + symbol);
		}
	});
	$(document).on("click", ".b_plus", function(){
		count = parseFloat($(this).parent().siblings(".int").val());
		symbol = $(this).parent().siblings(".int").data("symbol");
		step = $(this).parent().siblings(".int").data("step");
		if(symbol == "" || symbol == undefined){
			symbol = "";
		}
		if(step == "" || step == undefined){
			step = 1;
		}
		if(count == "" || isNaN(count) == true){
			count = 0;
		}
		count = count + step;
		if(count > 100){
			count = 100;
		}
		nval = parseFloat($(this).parent().parent().siblings(".int").val()) - 1;
		$(this).parent().parent().siblings(".int").val(nval + symbol);
		$(this).parent().siblings(".int").val(count + symbol);
	});
	//Remove address
	$("#mixer_step2").on("click", ".del", function(){
		$(this).parent().parent().remove();
		count = $("#mixer_step2 .box .row").length;
		if(count != 0){
		if(count == 1){
			document.getElementById("fprecent").value = "100%";
		}else if(count == 2){
			document.getElementById("fprecent").value = "90%";
		}else if(count == 3){
			document.getElementById("fprecent").value = "80%";
		}else if(count == 4){
			document.getElementById("fprecent").value = "70%";
		}else if(count == 5){
			document.getElementById("fprecent").value = "60%";
		}else if(count == 6){
			document.getElementById("fprecent").value = "50%";
		}else if(count == 7){
			document.getElementById("fprecent").value = "40%";
		}
		else if(count == 8){
			document.getElementById("fprecent").value = "30%";
		}
		else if(count == 9){
			document.getElementById("fprecent").value = "20%";
		}
		if(amount > 100){
			amount = 100;
		}
		if(amount == 100){
			document.getElementById("first").style.visibility = "hidden";
		}
		}
	});
	
	//Copy
	$(".copy").click(function(){
		new Clipboard(".copy");
	});
	
	//Reload
	$(".reload").click(function(){
		location.reload(true);
	});
	
	//Select
	if($(".select").length){
		$(".select select").each(function (i) {
			var SelectText = $(this).find("option:selected").text();
			$(this).parent().find(".int").val(SelectText);
		});
		$(".select .int").show();
		$(".select select").css({ opacity: 0 });
		$(".select select").change(function(){
			var SelectText = $(this).find("option:selected").text();
			$(this).parent().find(".int").val(SelectText);
		});
	}

	//Checkbox
	if($(".checkbox").length){
		$(".checkbox input").css({ opacity: 0 });
		$(".checkbox input").change(function(){
			if($(this).prop("checked") == true) {
				$(this).parent(".checkbox").addClass("check_act");
			} else {
				$(this).parent(".checkbox").removeClass("check_act");
			}
		});
		$('.checkbox input[type="checkbox"]:checked').parent(".checkbox").addClass("check_act");
	}

	//Radio
	if($(".radio").length){
		$(".radio input").css({ opacity: 0 });
		$(".radio input").change(function(){
			name = $(this).attr("name");
			$('input[name="' + name + '"]').parent(".radio").removeClass("radio_act");
			$(this).parent(".radio").addClass("radio_act");
		});
		$('.radio input[type="radio"]:checked').parent(".radio").addClass("radio_act");
	}
});

function outputUpdate(days) {
	var input = document.getElementById("hyipCalcDays");
	document.querySelector('#hyipCalcDays').value = days;
	input.onkeyup();
}