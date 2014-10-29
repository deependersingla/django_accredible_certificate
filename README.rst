Documentation for plugin install

1) Clone the accredible_certificate folder from this repo inside lms/djanogapps.

2) Edit lms/envs/common.py around line 1326 you will see installed apps, include accredible_certificate also there.

3) Visit https://accredible.com/issuer/sign_up and get one API KEY, its free :)

4) Run this command: sudo -u www-data /edx/bin/python.edxapp ./manage.py lms --settings aws generate_accredible_certs -c <course_id> -a <API_KEY>
e.g: sudo -u www-data /edx/bin/python.edxapp ./manage.py lms --settings aws generate_accredible_certs -c edX/DemoX/Demo_Course -a accredible_api_key

