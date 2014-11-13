INSTALLATION 

1) Copy the accredible_certificate folder from this repo inside your edx-platform lms/djanogapps.

2) Edit lms/envs/common.py around line 1326 you will see installed apps, include accredible_certificate also there.

3) Visit https://accredible.com/issuer/sign_up and get one API KEY, its free :)

 IF you also run rolling cetificate also then you need to do two more change:
 1) Update Views file from lms/djangoapps/certificates to the views.py given in this repo.
 2) In new views file Add API key at line 32

Using the Repo:
Login to the server and change to the /edx/app/edxapp/edx-platform directory to use manage.py
 1) Change in default styling of certifcate for a particular course:
      a) Command: sudo -u www-data /edx/bin/python.edxapp ./manage.py lms --settings aws generate_accredible_certs -c edX/DemoX/Demo_Course -a "API_KEY" -s True
      
      b) After this go to your Managemenrt console and desgin certificate. Click on publish.  All the course students are notified for their certificate.
      
      c) In the console command:  sudo -u www-data /edx/bin/python.edxapp ./manage.py lms --settings aws change_accredible_certs_status -c edX/DemoX/Demo_Course
         This command changes status of generating certificate from generating to download. Now student can see the Accredible certificate in lms also.
   
 2) No change in default styling from Provider level style preferences:
     Just run this command: sudo -u www-data /edx/bin/python.edxapp ./manage.py lms --settings aws generate_accredible_certs -c edX/DemoX/Demo_Course -a accredible_secret123

For rolling Certificate no change it will work the way, they are working now, after installation. If you want to update any of the certificate
visit management console or use Accredible API.

For any doubt please send a email to deepender281190@gmail.com or support@accredible.com. You will get reply in no time.
