---
# vim: set ft=markdown :
layout: default
title: Nerdistic Behaviour Disorder Test
permalink: /nerd-test/
---
<script type="text/javascript">
    function results(){
    	var choices = $('input:radio:checked');
    	var values = {
    		 0: [0,0.5,1,1.5,2],
    		 1: [0,0.5,1,1.5,2],
    		 2: [0,0.5,1,1.5,2],
    		 3: [2,1.5,1,0.5,0],
    		 4: [2,1.5,1,0.5,0],
    		 5: [0,0.5,1,1.5,2],
    		 6: [0,0.5,1,1.5,2],
    		 7: [2,1.5,1,0.5,0],
    		 8: [0,0.5,1,1.5,2],
    		 9: [0,0.5,1,1.5,2],
    		10: [0,0.5,1,1.5,2],
    		11: [0,0.5,1,1.5,2],
    		12: [2,1.5,1,0.5,0],
    		13: [0,0.5,1,1.5,2],
    		14: [2,1.5,1,0.5,0],
    		15: [0,0.5,1,1.5,2],
    		16: [0,0.5,1,1.5,2],
    		17: [0,0.5,1,1.5,2],
    		18: [0,0.5,1,1.5,2],
    		19: [0,0.5,1,1.5,2],
    		20: [0,0.5,1,1.5,2]
    	}

    	var nLine = function(i){
    		var lines = ["You have answered this test in such a way to suggest that you are not a nerd.", "You have answered this test in such a way to suggest that you are <i>possibly</i> a nerd, but it is not likely. While you displayed nerd traits, you appear to be almost normal.", "You have answered this test in such a way to suggest that you are <i>probably</i> a nerd. Please consult your doctor for more information.", "You have answered this test in such a way to suggest that you are <i>definitely</i> a nerd. <u>Seek help immediately.</u>"];
    		if (i > 10) return lines[Math.round(i/10)-1];
    		else return lines[Math.round(i/10)];
    	}

    	var ossLine = function(i){
    		var lines = ["You do not appear to be infected by open source software.", "You appear to have some open source software tendencies.", "You appear to have some open source software tendencies." ,"You appear to have abnormal open source software tendencies.", "You appear to have extreme open source software tendencies. <u>Seek help immediately.</u>"];

    		if (i > 2) return lines[Math.round(i/2)-1];
    		else return lines[Math.round(i/2)];
    	}

    	var result = function(){
    		var nerdTotal = ossTotal = Cur = 0;
    		for (var i = 0; i < choices.length; i++) {
    			var qNum = choices[i].name.slice(9);
    			cur = values[qNum][choices[i].value];
    			nerdTotal += cur;
    			if (['8','11','12','13','17'].indexOf(qNum) > -1)
    				ossTotal += cur;
    		};
    		return [nerdTotal, ossTotal]
    	}();

    	$('.table-responsive').slideUp(1200,'swing', function(){
    		document.getElementById('result').innerHTML = "<p>You have scored <b>" + result[0] + "</b> on the Nerdistic Behaviour Disorder index.</p> <p>"
    		document.getElementById('result').innerHTML += nLine(result[0]) + "</p> <p>";
    		document.getElementById('result').innerHTML += "For the OSSA (Open Source Software Addiction) index, you scored <b>" + result[1] + "</b> " + ossLine(result[1]) + "</p>";
    		document.getElementById('result').innerHTML += "<a href='#' onclick='reset()'>Take the test again?</a>"
    		$('#result').show(1300, 'swing');
    	});
    }
    function reset(){
    	$('#result').slideUp(1300, 'swing', function(){
    		$('#result').html('');
    		$('.table-responsive').slideDown(1300);
    		$('.btn-primary').slideDown();
    	})
    }
</script>

<div class="container">
    <div class="table-responsive">
        <table class="table table-hover table-striped">
            <thead>
                <tr>
                    <th>Statement</th>
                    <th>Agree factor</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>The Internet is the future.</td>
                    <td>
                        <input id="question_0_0" type="radio" name="question_0" value="0">
                        <label for="question_0_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_0_1" type="radio" name="question_0" value="1">
                        <label for="question_0_1">
                            Disagree </label>
                        <br>
                        <input id="question_0_2" type="radio" name="question_0" value="2">
                        <label for="question_0_2">
                            Neutral </label>
                        <br>
                        <input id="question_0_3" type="radio" name="question_0" value="3">
                        <label for="question_0_3">
                            Agree </label>
                        <br>
                        <input id="question_0_4" type="radio" name="question_0" value="4">
                        <label for="question_0_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I enjoy watching anime and/or reading manga.</td>
                    <td>
                        <input id="question_1_0" type="radio" name="question_1" value="0">
                        <label for="question_1_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_1_1" type="radio" name="question_1" value="1">
                        <label for="question_1_1">
                            Disagree </label>
                        <br>
                        <input id="question_1_2" type="radio" name="question_1" value="2">
                        <label for="question_1_2">
                            Neutral </label>
                        <br>
                        <input id="question_1_3" type="radio" name="question_1" value="3">
                        <label for="question_1_3">
                            Agree </label>
                        <br>
                        <input id="question_1_4" type="radio" name="question_1" value="4">
                        <label for="question_1_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I enjoy playing the game Minecraft.</td>
                    <td>
                        <input id="question_2_0" type="radio" name="question_2" value="0">
                        <label for="question_2_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_2_1" type="radio" name="question_2" value="1">
                        <label for="question_2_1">
                            Disagree </label>
                        <br>
                        <input id="question_2_2" type="radio" name="question_2" value="2">
                        <label for="question_2_2">
                            Neutral </label>
                        <br>
                        <input id="question_2_3" type="radio" name="question_2" value="3">
                        <label for="question_2_3">
                            Agree </label>
                        <br>
                        <input id="question_2_4" type="radio" name="question_2" value="4">
                        <label for="question_2_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I have had many girlfriends/boyfriends in the past.</td>
                    <td>
                        <input id="question_3_0" type="radio" name="question_3" value="0">
                        <label for="question_3_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_3_1" type="radio" name="question_3" value="1">
                        <label for="question_3_1">
                            Disagree </label>
                        <br>
                        <input id="question_3_2" type="radio" name="question_3" value="2">
                        <label for="question_3_2">
                            Neutral </label>
                        <br>
                        <input id="question_3_3" type="radio" name="question_3" value="3">
                        <label for="question_3_3">
                            Agree </label>
                        <br>
                        <input id="question_3_4" type="radio" name="question_3" value="4">
                        <label for="question_3_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I have had sexual intercourse with many members of the opposite sex.</td>
                    <td>
                        <input id="question_4_0" type="radio" name="question_4" value="0">
                        <label for="question_4_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_4_1" type="radio" name="question_4" value="1">
                        <label for="question_4_1">
                            Disagree </label>
                        <br>
                        <input id="question_4_2" type="radio" name="question_4" value="2">
                        <label for="question_4_2">
                            Neutral </label>
                        <br>
                        <input id="question_4_3" type="radio" name="question_4" value="3">
                        <label for="question_4_3">
                            Agree </label>
                        <br>
                        <input id="question_4_4" type="radio" name="question_4" value="4">
                        <label for="question_4_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I spend a lot of time on the computer.</td>
                    <td>
                        <input id="question_5_0" type="radio" name="question_5" value="0">
                        <label for="question_5_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_5_1" type="radio" name="question_5" value="1">
                        <label for="question_5_1">
                            Disagree </label>
                        <br>
                        <input id="question_5_2" type="radio" name="question_5" value="2">
                        <label for="question_5_2">
                            Neutral </label>
                        <br>
                        <input id="question_5_3" type="radio" name="question_5" value="3">
                        <label for="question_5_3">
                            Agree </label>
                        <br>
                        <input id="question_5_4" type="radio" name="question_5" value="4">
                        <label for="question_5_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I use the Linux operating system at home.</td>
                    <td>
                        <input id="question_6_0" type="radio" name="question_6" value="0">
                        <label for="question_6_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_6_1" type="radio" name="question_6" value="1">
                        <label for="question_6_1">
                            Disagree </label>
                        <br>
                        <input id="question_6_2" type="radio" name="question_6" value="2">
                        <label for="question_6_2">
                            Neutral </label>
                        <br>
                        <input id="question_6_3" type="radio" name="question_6" value="3">
                        <label for="question_6_3">
                            Agree </label>
                        <br>
                        <input id="question_6_4" type="radio" name="question_6" value="4">
                        <label for="question_6_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I use the Mac OS X operating system at home.</td>
                    <td>
                        <input id="question_7_0" type="radio" name="question_7" value="0">
                        <label for="question_7_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_7_1" type="radio" name="question_7" value="1">
                        <label for="question_7_1">
                            Disagree </label>
                        <br>
                        <input id="question_7_2" type="radio" name="question_7" value="2">
                        <label for="question_7_2">
                            Neutral </label>
                        <br>
                        <input id="question_7_3" type="radio" name="question_7" value="3">
                        <label for="question_7_3">
                            Agree </label>
                        <br>
                        <input id="question_7_4" type="radio" name="question_7" value="4">
                        <label for="question_7_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>It is important to encourage people and businesses to make their software open source.</td>
                    <td>
                        <input id="question_8_0" type="radio" name="question_8" value="0">
                        <label for="question_8_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_8_1" type="radio" name="question_8" value="1">
                        <label for="question_8_1">
                            Disagree </label>
                        <br>
                        <input id="question_8_2" type="radio" name="question_8" value="2">
                        <label for="question_8_2">
                            Neutral </label>
                        <br>
                        <input id="question_8_3" type="radio" name="question_8" value="3">
                        <label for="question_8_3">
                            Agree </label>
                        <br>
                        <input id="question_8_4" type="radio" name="question_8" value="4">
                        <label for="question_8_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>My Little Pony is not just a show for young girls.</td>
                    <td>
                        <input id="question_9_0" type="radio" name="question_9" value="0">
                        <label for="question_9_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_9_1" type="radio" name="question_9" value="1">
                        <label for="question_9_1">
                            Disagree </label>
                        <br>
                        <input id="question_9_2" type="radio" name="question_9" value="2">
                        <label for="question_9_2">
                            Neutral </label>
                        <br>
                        <input id="question_9_3" type="radio" name="question_9" value="3">
                        <label for="question_9_3">
                            Agree </label>
                        <br>
                        <input id="question_9_4" type="radio" name="question_9" value="4">
                        <label for="question_9_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I often complete tasks using the Terminal or Command Prompt.</td>
                    <td>
                        <input id="question_10_0" type="radio" name="question_10" value="0">
                        <label for="question_10_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_10_1" type="radio" name="question_10" value="1">
                        <label for="question_10_1">
                            Disagree </label>
                        <br>
                        <input id="question_10_2" type="radio" name="question_10" value="2">
                        <label for="question_10_2">
                            Neutral </label>
                        <br>
                        <input id="question_10_3" type="radio" name="question_10" value="3">
                        <label for="question_10_3">
                            Agree </label>
                        <br>
                        <input id="question_10_4" type="radio" name="question_10" value="4">
                        <label for="question_10_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I have a seemingly natural preference for open source software (over proprietary software).</td>
                    <td>
                        <input id="question_11_0" type="radio" name="question_11" value="0">
                        <label for="question_11_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_11_1" type="radio" name="question_11" value="1">
                        <label for="question_11_1">
                            Disagree </label>
                        <br>
                        <input id="question_11_2" type="radio" name="question_11" value="2">
                        <label for="question_11_2">
                            Neutral </label>
                        <br>
                        <input id="question_11_3" type="radio" name="question_11" value="3">
                        <label for="question_11_3">
                            Agree </label>
                        <br>
                        <input id="question_11_4" type="radio" name="question_11" value="4">
                        <label for="question_11_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I believe proprietary software is always better than open source software, by definition.</td>
                    <td>
                        <input id="question_12_0" type="radio" name="question_12" value="0">
                        <label for="question_12_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_12_1" type="radio" name="question_12" value="1">
                        <label for="question_12_1">
                            Disagree </label>
                        <br>
                        <input id="question_12_2" type="radio" name="question_12" value="2">
                        <label for="question_12_2">
                            Neutral </label>
                        <br>
                        <input id="question_12_3" type="radio" name="question_12" value="3">
                        <label for="question_12_3">
                            Agree </label>
                        <br>
                        <input id="question_12_4" type="radio" name="question_12" value="4">
                        <label for="question_12_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>Software licenses are a factor for me when choosing and downloading new software.</td>
                    <td>
                        <input id="question_13_0" type="radio" name="question_13" value="0">
                        <label for="question_13_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_13_1" type="radio" name="question_13" value="1">
                        <label for="question_13_1">
                            Disagree </label>
                        <br>
                        <input id="question_13_2" type="radio" name="question_13" value="2">
                        <label for="question_13_2">
                            Neutral </label>
                        <br>
                        <input id="question_13_3" type="radio" name="question_13" value="3">
                        <label for="question_13_3">
                            Agree </label>
                        <br>
                        <input id="question_13_4" type="radio" name="question_13" value="4">
                        <label for="question_13_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I supported Obama in the 2012 United States presidential election.</td>
                    <td>
                        <input id="question_14_0" type="radio" name="question_14" value="0">
                        <label for="question_14_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_14_1" type="radio" name="question_14" value="1">
                        <label for="question_14_1">
                            Disagree </label>
                        <br>
                        <input id="question_14_2" type="radio" name="question_14" value="2">
                        <label for="question_14_2">
                            Neutral </label>
                        <br>
                        <input id="question_14_3" type="radio" name="question_14" value="3">
                        <label for="question_14_3">
                            Agree </label>
                        <br>
                        <input id="question_14_4" type="radio" name="question_14" value="4">
                        <label for="question_14_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I identify with an unpopular/unusual political ideology (such as libertarianism).</td>
                    <td>
                        <input id="question_15_0" type="radio" name="question_15" value="0">
                        <label for="question_15_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_15_1" type="radio" name="question_15" value="1">
                        <label for="question_15_1">
                            Disagree </label>
                        <br>
                        <input id="question_15_2" type="radio" name="question_15" value="2">
                        <label for="question_15_2">
                            Neutral </label>
                        <br>
                        <input id="question_15_3" type="radio" name="question_15" value="3">
                        <label for="question_15_3">
                            Agree </label>
                        <br>
                        <input id="question_15_4" type="radio" name="question_15" value="4">
                        <label for="question_15_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>The NSA probably has records on me.</td>
                    <td>
                        <input id="question_16_0" type="radio" name="question_16" value="0">
                        <label for="question_16_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_16_1" type="radio" name="question_16" value="1">
                        <label for="question_16_1">
                            Disagree </label>
                        <br>
                        <input id="question_16_2" type="radio" name="question_16" value="2">
                        <label for="question_16_2">
                            Neutral </label>
                        <br>
                        <input id="question_16_3" type="radio" name="question_16" value="3">
                        <label for="question_16_3">
                            Agree </label>
                        <br>
                        <input id="question_16_4" type="radio" name="question_16" value="4">
                        <label for="question_16_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>Open source software is often more secure than closed source software.</td>
                    <td>
                        <input id="question_17_0" type="radio" name="question_17" value="0">
                        <label for="question_17_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_17_1" type="radio" name="question_17" value="1">
                        <label for="question_17_1">
                            Disagree </label>
                        <br>
                        <input id="question_17_2" type="radio" name="question_17" value="2">
                        <label for="question_17_2">
                            Neutral </label>
                        <br>
                        <input id="question_17_3" type="radio" name="question_17" value="3">
                        <label for="question_17_3">
                            Agree </label>
                        <br>
                        <input id="question_17_4" type="radio" name="question_17" value="4">
                        <label for="question_17_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I believe NSA cyber surveillance programs should be defunded or made illegal.</td>
                    <td>
                        <input id="question_18_0" type="radio" name="question_18" value="0">
                        <label for="question_18_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_18_1" type="radio" name="question_18" value="1">
                        <label for="question_18_1">
                            Disagree </label>
                        <br>
                        <input id="question_18_2" type="radio" name="question_18" value="2">
                        <label for="question_18_2">
                            Neutral </label>
                        <br>
                        <input id="question_18_3" type="radio" name="question_18" value="3">
                        <label for="question_18_3">
                            Agree </label>
                        <br>
                        <input id="question_18_4" type="radio" name="question_18" value="4">
                        <label for="question_18_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>Richard Stallman (founder of the Free Software Foundation) means well.</td>
                    <td>
                        <input id="question_19_0" type="radio" name="question_19" value="0">
                        <label for="question_19_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_19_1" type="radio" name="question_19" value="1">
                        <label for="question_19_1">
                            Disagree </label>
                        <br>
                        <input id="question_19_2" type="radio" name="question_19" value="2">
                        <label for="question_19_2">
                            Neutral </label>
                        <br>
                        <input id="question_19_3" type="radio" name="question_19" value="3">
                        <label for="question_19_3">
                            Agree </label>
                        <br>
                        <input id="question_19_4" type="radio" name="question_19" value="4">
                        <label for="question_19_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
                <tr>
                    <td>I use Tox for communicating with my friends and/or family.</td>
                    <td>
                        <input id="question_20_0" type="radio" name="question_20" value="0">
                        <label for="question_20_0">
                            Strongly disagree </label>
                        <br>
                        <input id="question_20_1" type="radio" name="question_20" value="1">
                        <label for="question_20_1">
                            Disagree </label>
                        <br>
                        <input id="question_20_2" type="radio" name="question_20" value="2">
                        <label for="question_20_2">
                            Neutral </label>
                        <br>
                        <input id="question_20_3" type="radio" name="question_20" value="3">
                        <label for="question_20_3">
                            Agree </label>
                        <br>
                        <input id="question_20_4" type="radio" name="question_20" value="4">
                        <label for="question_20_4">
                            Strongly agree </label>
                        <br>
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
    <div class="results" id="result" style="display: none;">
    </div>
    <input class="btn btn-primary btn-lg" name="submit" type="submit" onclick="results(); $(this).slideUp();" value="Get Results">
</div>