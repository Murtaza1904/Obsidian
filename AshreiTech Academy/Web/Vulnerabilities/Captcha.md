To prevent bots
- Login page
- Web scrapping

### Types of captcha
- text base captcha
- image base captcha
- checkbox captcha
- invisible captcha

### Captcha failure
- Captcha response not validating on server side
	- Remove captcha parameter
	- Change name of captcha parameter
- Captcha reuse (one time use)
- Empty captcha value accepted (null value/ zero value)
- HTTP method change (POST to GET)
- Expire captcha reuse

*Note: Test rate limiting after captcha bypass* 