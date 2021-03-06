TowerData Personalization API - Python
==================

For documentation of TowerData's API, visit
http://intelligence.towerdata.com/developers/personalization-api/personalization-api-documentation

How to Use
==========

Installation
------------

> pip install towerDataApi

Usage
-----
 
    from towerDataApi import TowerDataApi
    api = TowerDataApi.TowerDataApi('API_KEY')
    api.query_by_email('test@example.com')
    {u'gender': u'Male', u'age': u'25-34'}

Query Options
-------------
The egg supports several ways to query TowerData's API: email, hashed email (either MD5 or SHA1 hash), name and postal (NAP), or name and ZIP+4 (NAZ).

### query_by_email(self, email, hash_email = False)

This method queries TowerData's API with the specified email. 
If the hash_email option is set, then the email will be hashed before it's sent to TowerData.

### query_by_md5(self, md5_email)
### query_by_sha1(self, sha1_email)

These methods query TowerData's API with the specified email hashes (either MD5 or SHA1, respectively). 
 
### query_by_nap(self, first, last, street, city, state, email = None)

This method queries TowerData's API with a name and postal address: first name, last name, street, city, and state acronym (i.e., the state's 2-character postal code).
An optional email address may be provided to increase the match rate.

### query_by_naz(self, first, last, zip4, email = None)

This method queries TowerData's API with a name and ZIP+4 code. The ZIP+4 is a string with a 5-digit ZIP code and 4-digit extension separated by a dash.
An optional email address may be provided to increase the match rate.

Contributing
============
If you have suggestions or patches, feel free to email us at
<developer at towerdata dot com>. We look forward to hearing from you!


Contributors
============
Nicole Allard <nicole at rapleaf dot com>
Bojan  Milosavljevic <milboj at gmail dot com>

Dependencies
============
urllib3

> pip install urllib3

or visit the url https://github.com/shazow/urllib3/zipball/master.
Once you've unzipped the download, open a terminal window and navigate to the folder into which you unzipped the download. When you open the folder, one of the subdirectories is 'urllib3.' Open it. It contains a script called setup.py which you'll run via the command 'python setup.py install'.

Note that, on unsuccessful requests, we raise an error. Unsuccessful requests are any requests which send back an http response status outside of the range 200 <= status < 300.

License
=======
* The TowerData Personalization API has separate terms and conditions, which can
  be found at http://intelligence.towerdata.com/terms_and_conditions
* If you send us code, please keep in mind that it will be distributed under
  the same license as the rest of the project.
* This code is licensed under the Apache License which follows...

Copyright 2014 TowerData

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
