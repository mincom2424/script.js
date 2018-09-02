var current_index = 0 ;
 
var questionnaire = new Array();
 
 
//QUESTION 1
questionnaire[0] = new Array();
questionnaire[0][0] = "Question 1 ?";
questionnaire[0][1] = "images/monImage.png";
questionnaire[0][2] = new Array("Reponse 1","Reponse 2","Reponse 3","Reponse 4");
//on va conserver la bonne réponse, ou alors l'index de la bonne réponse.
questionnaire[0][3] = "Reponse 2";
 
 
//QUESTION 2
questionnaire[1] = new Array();
questionnaire[1][0] = "Question 2 ?";
questionnaire[1][1] = "images/monImage.png";
questionnaire[1][2] = new Array("Reponse 1","Reponse 2","Reponse 3","Reponse 4");
//on va conserver la bonne réponse, ou alors l'index de la bonne réponse.
questionnaire[1][3] = "Reponse 4";
 
 
//QUESTION 3
questionnaire[2] = new Array();
questionnaire[2][0] = "Question 3 ?";
questionnaire[2][1] = "images/monImage.png";
questionnaire[2][2] = new Array("Reponse 1","Reponse 2","Reponse 3","Reponse 4");
//on va conserver la bonne réponse, ou alors l'index de la bonne réponse.
questionnaire[2][3] = "Reponse 1";
 
function compare(a,b){
	if (a == b){
		alert("bonne réponse");
 
		if ( current_index+1 == questionnaire.length){
			alert("Questionnaire Finis, on revient au debut");
			show_quizz(0);
		}else{
			show_quizz((current_index+1));
		}
	}else{
		alert("mauvaise réponse");
	}
 
}
 
function show_quizz(index){
current_index = index;
document.getElementById("question").innerHTML = questionnaire[index][0];
document.getElementById("img").src = questionnaire[index][1];
reponses = document.getElementById("reponses");
reponses.innerHTML = "";
for (var i = 0; i < questionnaire[index][2].length ; i++){
	reponses.innerHTML += "<input type='button' value='"+questionnaire[index][2][i]+"' onclick=\"compare(\'"+questionnaire[index][2][i]+"\',\'"+questionnaire[index][3]+"\');\" />";
 
}
 
}
