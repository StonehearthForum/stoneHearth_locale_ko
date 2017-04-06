# startermod_locale (한글판)


#1. 업데이트 : 
해당 오버라이드 메소드들은 어떠한 모드에서도 적용될 수 있습니다.


#2. 모드에 대해서:
이 모드는 스톤하스 바닐라 상태에서 새로운 언어를 추가하는 기능을 가지고 있습니다.


#3. 모드가 작동하기 위해 설정해야 할 부분:
1) startermod_locale / manifest.json 언어 모딩 라인 추가.
   "mixintos" : {
      "stonehearth/locales/supported_languages.json" : "file(added_languages.json)"
   }

2) added_languages.json - 새로운 언어 추가.
   "languages": {
      "ko": {
         "display_name": "Korean(한국어)"
      }
   }

3) startermod_locale / manifest.json - 번역될 json 파일과 font 파일을 오버라이드.
   "overrides": {
   	  "stonehearth/ui/root/css/fonts/autourone/AutourOne-Regular-webfont.ttf" : "file(fonts/BMJUA.ttf)",
   	  "stonehearth/ui/root/css/fonts/autourone/AutourOne-Regular-webfont.woff" : "file(fonts/BMJUA.woff)",
   	  "stonehearth/ui/root/css/fonts/grobold/grobold-webfont.ttf" : "file(fonts/BMJUA.ttf)",
   	  "stonehearth/ui/root/css/fonts/grobold/grobold-webfont.woff" : "file(fonts/BMJUA.woff)",
   
	  "debugtools/locales/ko.json": "file(translations/debugtools/ko.json)",
      "stonehearth/locales/ko.json": "file(translations/stonehearth/ko.json)",
	  "rayyas_children/locales/ko.json": "file(translations/rayyas_children/ko.json)"
   }

   
#4. 노트
만약 해당 모드가 설치 이후, 바로 작동하게끔 하려면 디폴트 언어로 설정할 필요가 있습니다. 방법은 아래와 같습니다.
   {
	   "info" : {
		  "name" : "stoneHearth_locale_ko", 
		  "version" : 170407
	     },
	    "default_locale": "ko",
   }

   
#5. en.json 파일은 어떻게 번역해야 하나요?
json 파일의 콜론 ' : ' 오른쪽에 오는 문장만 변경하면 됩니다.  
콜론 ' : ' 왼쪽의 단어와  대괄호 '[ ] ' 에 둘러쌓인 변수명은 변경하지 마세요.
 http://codebeautify.org/jsonviewer  웹사이트를 사용하여 해당 데이터 구조를 더욱 쉽게 볼 수 있습니다.

한국어는 아래와 같이 변경하면 됩니다 :
  "ai": {
   "actions": {
      "status_text": {
         "chase_entity": "[name(data.target)]를 추적한다.",
		 
		 
#6. 참조
이 가이드는 네이버 스톤하스 포럼 카페에서 작성되었습니다.
http://http://cafe.naver.com/stonehearth  
