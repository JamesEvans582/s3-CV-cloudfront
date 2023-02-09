# s3-CV-cloudfront
Static web hosting / s3 / Cloudfront

So created an basic HTML/CSS website cv using visual studio code. 
Keep them safe in a the folder for later.

1) Firstly log into the AWS console and create an S3 bucket
2) <img width="1792" alt="Screenshot 2023-02-09 at 13 52 43" src="https://user-images.githubusercontent.com/71371405/217868146-a1faedf3-d2c2-4a83-a2aa-4fed0d6396f8.png">

2) You can leave all the settings as standard, including block all persmissions, don't want people acessing your s3 bucket.It will be Cloudfront that be distibuting the files from S3.
3<img width="1792" alt="Screenshot 2023-02-09 at 14 46 21" src="https://user-images.githubusercontent.com/71371405/217868506-a348478f-8046-4267-9d07-4bd6c581f8f9.png">

 
4) With this you should have your new titled folder, click the bucket and upload file. 
 <img width="1792" alt="Screenshot 2023-02-09 at 14 51 31" src="https://user-images.githubusercontent.com/71371405/217870189-b34a9c2d-9e07-4bcc-8ff5-bf1647c9a96b.png">



5) click the bucket - then upload - and add files.
<img width="1792" alt="Screenshot 2023-02-09 at 16 14 54" src="https://user-images.githubusercontent.com/71371405/217871146-2af1734a-c3ad-4729-a897-a06b054acf4b.png">

6) When we upload we will get a url, however, we don't have access the url due the file to bucket permissions. This is where cloudfront comes in.


7) load cloudfront within aws console - click create distribution - 
<img width="1792" alt="Screenshot 2023-02-09 at 15 20 23" src="https://user-images.githubusercontent.com/71371405/217871912-d0833363-5fa1-4b99-85c7-291bcaf4a9ec.png">

 8) when we click into the origin domain it will automatically see our S3 bucket in there, select the S3 bucket. Then under origin access select 'origin access control settings'. This means only cloudfront will have the option of accessing the S3 bucket. However we do have to connect them, this is via bucket policy.
<img width="1792" alt="Screenshot 2023-02-09 at 15 33 22" src="https://user-images.githubusercontent.com/71371405/217875823-e0485409-f472-4651-b7c4-d3fb4b073e5d.png">



9) We will then redirect to HTTP and HTTPS.There are a lot more options such as using Shield, setting TTL and prefixes but in this simple tutorial we'll leave as default. 
<img width="1028" alt="Screenshot 2023-02-08 at 13 37 38" src="https://user-images.githubusercontent.com/71371405/217877242-39b2c1bc-77c3-4582-a6de-93ebafb07dbe.png">


10) After we save changes AWS will give us the code to complete the bucket policy, which is read access for cloudfront to access s3. <img width="1792" alt="Screenshot 2023-02-08 at 13 39 45" src="https://user-images.githubusercontent.com/71371405/217878514-e3415fc0-b870-411b-b795-cba6484e30c0.png">

11) Once we have copied the code, we have to paste it in the bucket policy.
<img width="1792" alt="Screenshot 2023-02-08 at 13 41 01" src="https://user-images.githubusercontent.com/71371405/217879614-b8a09df0-b4e9-4e3a-ab00-960d9117b20c.png">

12) Once Cloudfront has distributed, if you copy the domain name, and add /index.html it should load. 
<img width="1792" alt="Screenshot 2023-02-09 at 16 55 27" src="https://user-images.githubusercontent.com/71371405/217883731-cf451982-2bd8-47a3-9487-717df311ddac.png">

Happy days! 


