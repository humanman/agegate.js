#JS Age Gate
This little guy was created to for a bunch of alchole related websites that I've worked on. The issue we faced using PHP as the Age Gate processor was caching - each and every page had to be validated and caused all sorts of issues. Hence what **JS Age Gate** was created.

###How to use:

As this needs to fire before any other code loads, it must to go in the header of the site and not as a seperate file include. It ***must*** parse straight away or else restricted content might be seen. 

Also, so that any other scripts can access it, I reccommend adding it as a global object

	window.AgeGate = new AgeGate(18,'afterDarkFilmMusicFood');

    var cookie = ADAgeGate.getCookie();
              
	if ( cookie && cookie === 'ageCheckVale=true' ){
		console.log('valid cookie, enjoy!');
	} else {
		// we has no cookies
		console.log('We has no cookie');
		if ( window.location.pathname !== '/age-gate/'){
			location = ADAgeGate.ageGateUrl;
		}
	}
	
And you're done!

Use this in conjunction with `<noscript>` in order to block what you don't want seen if the user has Javascript turned off