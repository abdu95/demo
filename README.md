# demo
DO all the steps again: SG, KP, Instance. (Later we can recognize objects and images, transcribe)
you can use putty to login to computers and see terminal

Open Putty, then Open AWS Instance. Copy Public IPv4 address
it does not matter to use Public IPv4 address OR Public IPv4 DNS. DNS gets translated into IP address.
Putty: SSH should be selected. put IP to hostname and to Saved Sessions

Click SSH >> Auth >> Private Key Authentication. Browse your PriK.
Then click Session >> SAVE

There is a computer that I do not know >> There is no Certificate. Yes (trust)
use mobile hotspot (to avoid Network error)
Error: software caused connection abort putty windows. The error Network error: Software caused connection abort from PuTTY is the result if there is an IP address conflict (two or more computers have the same IP address) on the network. ... In this particular case it could be an IP address conflict locally on the Windows 7 computer or with another device on the network.
username: ubuntu (Press Enter)

sudo apt update
sudo apt install moon-buggy
moon-buggy

sudo - super user (supervisor?)
update - updates package manager.
update all pakages available for ubuntu

> (why username is ubuntu?)

create a web server in your computer. NGINX
`sudo apt install nginx`

now in browser, type 18.202.25.119
because now instance has a web server.

why page not opening? because our server is not smart enough yet to handle requests.
also, you only want allow SSH. (so it says 'thank you but not thank you')

SecGroup >> Edit Inbound Rules >> HTTP (default port 80) >> Anywhere
Now it says Welcome to NGINX (when you again try to access your IP from browser)

`cd /var/www/html/`
`sudo nano index.nginx-debian.html`

services that amazon gives as a platform
storage: download and upload files >> S3

> EBS - Elastic Block Storage (fastest). It is like hard disks in cloud
> S3 - Simple Storage Service (Scalable)
> Glacier - for archiving (for anything that you can throw out later)

Go to Instance >> Storage (EBS. this storage is independednt from the instance)
you can shutdown computer, get disk, fire up new computer and attach this disk to that computer
S3 - for storing data and retrieving (e.g. FTP server, Dropbox)
Cross region replication. (Amazon replicates your file (why?), they ensure data will not be lost)
Netflix data stored on S3.

Amazon Console >> Storage >> S3
cloudtrail - monitors user activity, every click.

In S3, bucket is root folder. in S3, every folder name should be unique (globally). (heeey, here I can put my files)
Uncheck `Block all public access`. (it ensure leakage will not happen)

Versioning >> you pay to old and new file too. But you see only new file. you can version back to old version.

Standard-IA - when you dont want to access very often.

Read access to everyone.

https://aws.amazon.com/s3/pricing
First 50 TB / Month - 0.02GB
Mountain Duck >> use S3 as external driver

How much it costs to access file? >> Requests and data retrievals = $0.0004

Amazon wants you to lock down - send me as much data as you want, its free - adding data to S3 is free
If you want to stream/share data >> its $0.09 per GB

companies use S3 as data lake (raw data). Then they are building process to transform this data.
AzureBlobStorage is same as S3

S3 Glacier is extremely cheap. Deep Archive- you dont want to survey data.
Amazon: put data in Glacier if you need it even after 2 years, its cheap

https://aws.amazon.com/s3/storage-classes/?nc=sn&loc=3
Glacier: only can be restored within 12 hours.

you can do image recognition programmatically as well.

Object and scene detection
Confidence
Image moderation
Facial analysis
appears to be male 99%

Celebrity recognition - bezos

Face comparison
Text in image

PPE detection - person with mask

https://github.com/paws-r/paws
Paws is a Package for Amazon Web Services in R.
Platform as a aservice (you need engineer to get result)

https://www.youtube.com/watch?v=RVdNobKNMig
angry customer

https://ytmp3.cc/en13/ - youtube to mp3
Now you can transcribe mp3.
Transcription job task. you cant upload mp3 file, first you should upload file to S3.

Audio Identification (Speaker 0, Speaker 1)

Application Integration (API response. R. S3 location)

Amazon Comprehend - Natural Language Comprehension tool. (comprehension - понимание).
Sentiment - 0.94% confident negative conversation.

Insurance Company - analyze customer calls.
Google Cloud - Hungarian Language transcribe. 

Amazon Polly

HW: CNN vs. FOX >> to check out sentiment

Serverless RMDs

token to auth as user

When you want to access Services programmatically, you generate keypair (accessKey).
Do not put Access key ID to github repo. 
Security companies watching it. GitGuardian. I got an email right away. AWS Exposed. 
Also Amazon is sending alert. Issues >> Open Issues >> Amazon disabled or quarantiend this Access Key. 

Amazon_S3.Rmd

delete not existing object >> 404

What is system var? why we need it for polly?

it opens HTTP connection to Amazon server endpoint, gives text and gets reposnse.

detect_sentiment -- positive 98%

cloudyr - d1
paws-r

bad side is wea re working with Amazon API - it is not open-source (Amazon using this internally, each time we )

https://aws.amazon.com/translate/pricing/
$15.00 per million characters

https://aws.amazon.com/rekognition/pricing/


Medium >> Blogging platofrm

- US Elections
- Covid
