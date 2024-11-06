#### Title: [Login] User cannot login to app using correct credentials, gets "wrong email or password, try again" error

**Browser/Ver.**: Chrome Wersja 130.0.6723.92 (Oficjalna wersja) (arm64)\
**Build/branch**: https://app.interviewme.pl/\
**Device/OS**: MacOS Sonoma _21.37_\
**Also on PROD?**: YES

**Bug description**: When using valid credentials, both email and password, error message "wrong email or password, try again" appears and user is not logged in.\
**Preconditions**:   
- **email**: vincent-sqa+rekru2@bold.com
- **password**: parmezan6

**Repro steps**: 
1. Go to the url: https://app.interviewme.pl/login/
2. Fill in email and password fields with data provided above
3. Click "Login" button below form
4. See, that there is error message "wrong email or password, try again" 

**Actual result**: User gets error message "wrong email or password, try again", even when he tries to log in with valid credentials\
**Expected result**: User using valid credentials is able to log in to a app

**Additional Info**: Response from graphql and t request below\
__t__: (_i've only unroll properties which i thought is most important due to FALSE in "Login status"_ ):
```
{timestamp: "2024-11-06T12:11:15.355Z",…}
anonymousId
: 
"4e20b0d8-f13c-4e58-ace8-a8a800ec233d"
context
: 
{,…}
event
: 
"popup"
integrations
: 
{Google Analytics: false, FullStory: false, Fullstory: false}
messageId
: 
"ajs-next-1730895075355-2b6c715d-0e19-4cdb-9475-4af85cf000bd"
properties
: 
{Login Status: "FALSE",…}
$screen_height
: 
1117
$screen_width
: 
1728
Login Status
: 
"FALSE"
Platform
: 
"Web"
action
: 
"clicked"
activePlanName
: 
"none"
appArea
: 
"Builder - Resume"
builder type
: 
"resumes"
click option
: 
"sign up"
device type
: 
"desktop"
documentId
: 
"2a0c3cb6-4407-4b30-8f8d-ce32135881c8"
documentScore
: 
"0"
documentScoreLevel
: 
"LOW"
documentTemplate
: 
"cascade"
locale
: 
"pl-PL"
path
: 
"/app/rsme/2a0c3cb6-4407-4b30-8f8d-ce32135881c8/content/9a1ec7c3-6d9d-4bd6-91c4-cbdc1339078a"
popup name
: 
"Register"
url
: 
"https://app.interviewme.pl/app/rsme/2a0c3cb6-4407-4b30-8f8d-ce32135881c8/content/9a1ec7c3-6d9d-4bd6-91c4-cbdc1339078a"
userType
: 
"Guest"
viewName
: 
"Section - Personal"
visitId
: 
"cc2f38fe-499b-4834-bdc7-68fc5961b106"
sentAt
: 
"2024-11-06T12:11:15.369Z"
timestamp
: 
"2024-11-06T12:11:15.355Z"
type
: 
"track"
userId
: 
"0f23b161-1941-41d5-bda2-8540bffdd7f8"
writeKey
: 
"icw0nF96iQw2oA7MuHDE6uPbYsr4Fa0b"
_metadata
: 
{bundled: ["FullStory", "Hotjar", "Segment.io"], unbundled: [],…}
```

__graphql__:
```
{
    "data": {
        "user": {
            "status": "INVALID_CREDENTIALS",
            "userid": null,
            "emailid": null,
            "claims": null,
            "redirectUrl": null,
            "authToken": null,
            "additionalMessageType": null,
            "additionalMessage": null,
            "_openAPIToGraphQL": {
                "data": {
                    "user": {
                        "usedParams": {
                            "accountsUserDetailsInput": {
                                "OriginatingURL": "https%3A%2F%2Fapp.interviewme.pl%2Fapp%2Frsme%2F2a0c3cb6-4407-4b30-8f8d-ce32135881c8%2Fcontent%2F9a1ec7c3-6d9d-4bd6-91c4-cbdc1339078a",
                                "Referrer": "https%3A%2F%2Fcoderbyte.com%2F",
                                "guestUserID": "0f23b161-1941-41d5-bda2-8540bffdd7f8",
                                "password": "password_from_task",
                                "productCD": "NGB",
                                "userName": "<mail_from_task@bold.com"
                            }
                        },
                        "usedPayload": "{\"OriginatingURL\":\"https%3A%2F%2Fapp.interviewme.pl%2Fapp%2Frsme%2F2a0c3cb6-4407-4b30-8f8d-ce32135881c8%2Fcontent%2F9a1ec7c3-6d9d-4bd6-91c4-cbdc1339078a\",\"Referrer\":\"https%3A%2F%2Fcoderbyte.com%2F\",\"guestUserID\":\"0f23b161-1941-41d5-bda2-8540bffdd7f8\",\"password\":\"parmezan6\",\"productCD\":\"NGB\",\"userName\":\"vincent-sqa+rekru2@bold.com\"}",
                        "usedRequestOptions": {
                            "url": "https://accounts.interviewme.pl/accounts/v5/login",
                            "method": "post",
                            "headers": {
                                "content-type": "application/json",
                                "accept": "application/json",
                                "Cookie": "visitinfo=[City,Warsaw]&[State,14]&[Country,PL]&[PostalCode,00-510]&[BrowserName,Chrome]&[BrowserVersion,130]&[DeviceType,]&[OSName,macOS]&[DeviceModel,Macintosh]&[OSVersion,10.15.7]; vstr=b4ede478-3da8-4ac5-923e-dcba0d492ff7; ref=20802; vsuid=cc2f38fe-499b-4834-bdc7-68fc5961b106; vsutms=a6da33cd-e144-4f38-b68a-a91282bc6e0b#b4ede478-3da8-4ac5-923e-dcba0d492ff7#cc2f38fe-499b-4834-bdc7-68fc5961b106#1730891123#https://coderbyte.com#||||; vssessionuid=bf45137a-6b51-4081-ac55-71be7305884e; Auth=-Fy93S35QUlDGfmY-rbG5smphH_rUSTRdOsSaiPSCUG7_vYzfOA1RiUY7z5LSIYaGdiZh8Y1nPRC28KYjCA9qVHV3tXu6mDwOs5in2g2uISfY-eM7ZzlPqBqp09zLtHweFHwip95xyS3oJVAOzh9VFPQUWQj40IFL5WcaGy22pnNHoNYF5Z4GvzgQjEcec3muEEs_UoM40nOzWNo1EPY5ARztQy0W09Fi8w4O2rjz1rDNF7hoxjUP5gPuocLFkqsxcMIc2RCBp9D4hQ_MrrEwP_EjS5vCVaNizF1Hpl31-OXcAanpyGIonlT5EtYcStrcrIxJeGtWi7c_SEBKbrQPvqReAlKMU4mXgnILxdxe-2y6N2seV1nGRaJxwp7SVzXF9MPP-iDUWzviDiCULwRpA1VZ68-RfuGWMqpKSTCUfaka3dAmRO6isv9vWv0F2Mlwzbr4vNHqES-rXPCApF4m_Yu2Uggn7Brm42MQqjP0iW3Bqdn8ERQSSpXj1rQiaRhh82UJOQakhUqPxzdkIbFW0JWH3vKfF39TU1zYi9whWS55FxtFyB-KluTkzp-QAyz1pu9gH3F10MpuXthA586YPyFmRlMtNvwWCyPkdl1Wrhe2GLp3iKxYWiY2z0nK6npyLq1YP4xJZD0ub8eYYRz2dgcU19030_qZr_yWFPywmGlEzOMLRyvyAjNw1yRH_KRXs3v9q5V3V3ENMLt_MzpVAC3vR-Uz4dtUUU0MAnMvlQdE2DGhl6aUpVKIUm9mdpsq7lVZU3yROY5GFXcDt0rVgJ0XUNqoc-qJmAfCaRelffEFfHIj3c46r7jxRLC-5jnSwyEIE2TAklyHIEiaRvnL4SRbWyDeTFRute9BUlgO9t0mIYlYswZCwTKG3_E6z0JAsSQPUSh3sKo3KcD3iBDzoEJgqJkMz3ty8X5ObC0bk90YdsNGseAVhO-K5S96eEC5aVaqWzO91tzji3gj7pIwJ8YySVjBwfmO8Pr4sYTasLKStbhO4a5bM0QDPdulnYc; UserStatus={\"IsUserLoggedIn\":false,\"User\":{\"Role\":0,\"UserId\":\"0f23b161-1941-41d5-bda2-8540bffdd7f8\",\"AccDisplayName\":\"Guest\",\"CreatedOn\":\"11/6/2024 11:05:23 AM\"}}; acc_session={dc0e8ca0-2d7d-4355-ab61-eae75867327d}; ngb-attribution-headers={%22channel%22:%22referrer%22}; _gcl_au=1.1.1092947140.1730891124; fs_user=0; vstrType=1; COOKIE_CONSENT={%22key%22:null%2C%22accepted%22:true%2C%22consent%22:{%22analytics%22:true%2C%22personalization%22:true%2C%22advertising%22:true%2C%22necessary%22:true}%2C%22dateAllowed%22:1730891131107}; _gid=GA1.2.385200970.1730891131; ajs_anonymous_id=4e20b0d8-f13c-4e58-ace8-a8a800ec233d; ajs_user_id=0f23b161-1941-41d5-bda2-8540bffdd7f8; _hjSessionUser_219087=eyJpZCI6ImE3MDc0YjdlLTJhMDYtNTE2ZS1hMjA2LTI4NzY5NTU3ZDMwZiIsImNyZWF0ZWQiOjE3MzA4OTExMzE0OTAsImV4aXN0aW5nIjp0cnVlfQ==; _hjSession_219087=eyJpZCI6IjVkYmNjZjIwLTQ5ODgtNGIwNi04ZTA3LWM1NzI2M2ViMjg2MyIsImMiOjE3MzA4OTExMzE0OTEsInMiOjEsInIiOjAsInNiIjowLCJzciI6MCwic2UiOjAsImZzIjoxLCJzcCI6MH0=; _hjHasCachedUserAttributes=true; _ga=GA1.1.14900839.1730891131; _uetsid=09c487509c2f11ef9f5cf797c752b677; _uetvid=09c48f409c2f11ef9b21b12f23140155; _ga_H9EZWN0BP4=GS1.1.1730891131.1.1.1730891425.59.0.0",
                                "User-Agent": "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/130.0.0.0 Safari/537.36",
                                "Accept-Language": "pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7",
                                "Origin": "https://app.interviewme.pl",
                                "X-Site": "interviewme",
                                "X-Forwarded-For": "78.11.150.113,::ffff:192.168.1.39"
                            },
                            "qs": {},
                            "body": "{\"OriginatingURL\":\"https%3A%2F%2Fapp.interviewme.pl%2Fapp%2Frsme%2F2a0c3cb6-4407-4b30-8f8d-ce32135881c8%2Fcontent%2F9a1ec7c3-6d9d-4bd6-91c4-cbdc1339078a\",\"Referrer\":\"https%3A%2F%2Fcoderbyte.com%2F\",\"guestUserID\":\"0f23b161-1941-41d5-bda2-8540bffdd7f8\",\"password\":\"parmezan6\",\"productCD\":\"NGB\",\"userName\":\"vincent-sqa+rekru2@bold.com\"}"
                        },
                        "responseHeaders": {
                            "content-length": "165",
                            "content-type": "application/json; charset=utf-8",
                            "date": "Wed, 06 Nov 2024 12:11:15 GMT",
                            "server": "Microsoft-IIS/10.0",
                            "cache-control": "private",
                            "set-cookie": [
                                "visitinfo=[City,Warsaw]&[State,14]&[Country,PL]&[PostalCode,00-510]&[BrowserName,Chrome]&[BrowserVersion,130]&[DeviceType,]&[OSName,macOS]&[DeviceModel,Macintosh]&[OSVersion,10.15.7]; domain=.interviewme.pl; path=/; secure; SameSite=None",
                                "vsuid=cc2f38fe-499b-4834-bdc7-68fc5961b106; domain=.interviewme.pl; path=/; secure; SameSite=None",
                                "vsutms=a6da33cd-e144-4f38-b68a-a91282bc6e0b#b4ede478-3da8-4ac5-923e-dcba0d492ff7#cc2f38fe-499b-4834-bdc7-68fc5961b106#1730891123#https://coderbyte.com#||||; domain=.interviewme.pl; expires=Mon, 05-Nov-2029 12:11:15 GMT; path=/; secure; SameSite=None",
                                "vssessionuid=bf45137a-6b51-4081-ac55-71be7305884e; domain=.interviewme.pl; path=/; secure; SameSite=None"
                            ],
                            "x-aspnetmvc-version": "5.2",
                            "x-aspnet-version": "4.0.30319",
                            "x-powered-by": "ASP.NET"
                        }
                    }
                }
            }
        }
    }
}
```