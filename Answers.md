#Answers

## Prompt 1
As you have now been in the process of delivering and building your product, we'd like to know what has changed along the way:

Describe how the requirements of the features you have been building/designing have changed.
What caused these requirements to change?

Engineering Students: What types of architectural requirements changed? Did you have to make any trade-offs or add any new packages/libraries or dependencies to your application's technical stack in order to meet the new changes? 

**The requirement changes associated with this project have not been overt in terms of changes we have needed to make concerning our projects fundamental archiectecture. The changes that have been made though minute in comparision to the whole archietecture have been largely unseen necessities as opposed to archietectural trade-offs. For instance, we needed to add JWT decoding functionality to make initial user information requests on login in order to interface with the data Okta provides us during this step that allows us to request user data from our server in a secure manner. So we added a library that handles this. Another example would be that Okta, the third party service we are using for multifactor authentication, requires the client to generate a random string convert it to a base64 format, and then hash it using the SHA256 algorithm as part of its MF authentication process. This necessitated the used of a library which generated a random string (nano) and to do the conversion/hashing (browser-crypto) so those were added to the process. Furthermore many Okta request require the requests to be sent with a MIME type of "x-www-form-urlencoded" which uses a query string attached to an base url to facilitate information transfer, to streamline this process a object to querystring conversion library was used as objects are easier to reason about in javascript then querystrings are due to native support of that data structure. These examples are some of the main things which stand out to me in terms of changes to our project's archietecture, its core pieces (React, Redux, Apollo, Express, PostgresSQL) remain unmoved from their places.** 

