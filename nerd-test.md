---
# vim: set ft=markdown :
layout: default
title: Nerdistic Behaviour Disorder Test
permalink: /nerd-test/
---
<script type="text/javascript">
    function plot(plotData){
        var canvas = document.getElementById('canvas'), contex = canvas.getContext("2d"),
            colours = ["#C02942","#D95B43","#542437"],
            cX = canvas.width/2, cY = canvas.height/2, labels = ["Nerdistic behaviour", 'Political Affliations', 'OSS Addiction'],
            start = 0,
            total = Object.keys(plotData).reduce(function(sum, key){return sum + plotData[key]},0);
            contex.clearRect(0, 0, canvas.width, canvas.height);

            canvas.style.display = '';

            for (var i = 1; i < 4; i++) {
                var itemValue = plotData[i],
                    sliceSize = (itemValue/total)*Math.PI*2,
                    end = start + sliceSize,
                    mid = start + sliceSize/2;

                contex.save();
                contex.fillStyle = colours[i-1];
                contex.beginPath();
                contex.moveTo(cX,cY);
                contex.arc(cX,cY,canvas.height/3,start,end,false);
                contex.closePath();
                contex.fill();
                contex.font = "9pt Helvetica Neue";
              
                if (itemValue)  contex.fillText(labels[i-1], cX+ Math.cos(mid) * cX*0.65-45, cY + Math.sin(mid) * cY *0.78+7);

                start = end;
            }
    }



    function results(){
        var choices = $('input:radio:checked'),
            nerd = [0,0.25,0.50,0.75,1], notNerd = [1,0.75,0.5,0.25,0],
            ossQuestions = ['6','8','11','12','13','17'],
            values = {
             0: [nerd,1],
             1: [nerd,1],
             2: [nerd,1],
             3: [notNerd,1],
             4: [notNerd,1],
             5: [nerd,1],
             6: [nerd,3],
             7: [notNerd,3],
             8: [nerd,3],
             9: [nerd,1],
            10: [nerd,1],
            11: [nerd,3],
            12: [notNerd,3],
            13: [nerd,3],
            14: [notNerd,2],
            15: [nerd,2],
            16: [nerd,2],
            17: [nerd,3],
            18: [nerd,2],
            19: [nerd,3],
            20: [nerd,3]
        }

        var nLine = function(score){
            var lines = ["not a nerd.", "<i>possibly</i> a nerd, but it is not likely. While you displayed nerd traits, you appear to be almost normal.", "<i>probably</i> a nerd. Please consult your doctor for more information.", "<i>definitely</i> a nerd. <u>Seek help immediately.</u>"];

                r=.99*score/(Object.keys(values).length-1); 
                return lines[Math.floor(r*lines.length)] || lines[lines.length-1]
        }

        var ossLine = function(score){
            var lines = ["You do not appear to be infected by open source software.", "You appear to have some open source software tendencies.", "You appear to have some open source software tendencies." ,"You appear to have abnormal open source software tendencies.", "You appear to have extreme open source software tendencies. <u>Seek help immediately.</u>"];

                r=.99*score/(ossQuestions.length-1); 
                return lines[Math.floor(r*lines.length)] || lines[lines.length-1]
        }

        var result = (function(){
            var nerdTotal = ossTotal = Cur = 0,
                symTotal = {1: 0, 2:0, 3:0};
            for (var i = 0; i < choices.length; i++) {
                var qNum = choices[i].name.slice(9);
                cur = values[qNum][0][choices[i].value];
                symTotal[values[qNum][1]] += cur
                nerdTotal += cur;
                if (ossQuestions.indexOf(qNum) > -1)
                    ossTotal += cur;
            };
            return [nerdTotal, ossTotal, symTotal]
        })();

        $('.table-responsive').slideUp(1200,'swing', function(){
            document.getElementById('result').innerHTML += "<p>You have scored <b>" + result[0] + "</b> on the Nerdistic Behaviour Disorder index.</p> <p>"
            document.getElementById('result').innerHTML += "You have answered this test in such a way to suggest that you are " + nLine(result[0]) + "</p> <p>";
            document.getElementById('result').innerHTML += "For the OSSA (Open Source Software Addiction) index, you scored <b>" + result[1] + ".</b> " + ossLine(result[1]) + "</p>";
            document.getElementById('result').innerHTML += "<a href='#' onclick='reset()'>Take the test again?</a>"
            if (result[0]) plot(result[2]);
            $('#result').show(1300, 'swing');
        });
    }
    function reset(){
        $('#result').slideUp(1300, 'swing', function(){
            $('#result').html('<center><canvas id="canvas" width="600" height="400" style="display: none;"></center>');
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
        <center><canvas id="canvas" width="600" height="400" style="display: none;">
        </canvas></center>
    </div>
    <input class="btn btn-primary btn-lg" name="submit" type="submit" onclick="results(); $(this).slideUp();" value="Get Results">
</div>