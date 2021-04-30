$(document).ready(function(){
    typingTool = false;//조건문
    typingI = 0;//조건문 재료
  
    // 타이핑으로 사용할 텍스트를 가져온다 
    typingTxt = $(".typing_txt").text();
    typingTxt = typingTxt.split("");
    /*  
      split("자르기 기준",자르기 갯수)
      문자열을 자르고 오브젝트로 변환
      한글자씩 자른다.
    */

    console.log(typingTxt);
    
  // 타이핑이 진행되지 않았다면     
    if(typingTool == false){    
       var typing = setInterval(function(){
        // 타이핑될 텍스트 길이만큼 반복 
        if(typingI < typingTxt.length){
          // 한글자씩 이어준다. 
          $(".typing").append(typingTxt[typingI]); 
          typingI++;

          //console.log(typingI);
        }else{
          typingBool = true;// 끝내기 시도
        }       
      },100);// 반복동작    

    }else{
      clearInterval(typing); //끝나면 반복종료 
    }
});
