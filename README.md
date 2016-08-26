
Original source: [The blog article to accompany this project can be found here](http://www.cheynewallace.com/uploading-to-s3-with-angularjs/) 


CORS Configuration
-------------------
You will need to add a CORS policy to your AWS bucket to allow uploads from this app. Details on how to add this policy to your bucket can found in the blog mentioned above, under the CORS section
Here's a sample policy that you can use

```
<?xml version="1.0" encoding="UTF-8"?>
<CORSConfiguration xmlns="http://s3.amazonaws.com/doc/2006-03-01/">
    <CORSRule>
        <AllowedOrigin>http://localhost:3000</AllowedOrigin>
        <AllowedOrigin>https://www.yourdomain.com</AllowedOrigin>
        <AllowedOrigin>http://staging.yourdomain.com</AllowedOrigin>
        <AllowedMethod>PUT</AllowedMethod>
        <MaxAgeSeconds>3000</MaxAgeSeconds>
        <ExposeHeader>x-amz-server-side-encryption</ExposeHeader>
        <ExposeHeader>x-amz-request-id</ExposeHeader>
        <ExposeHeader>x-amz-id-2</ExposeHeader>
        <AllowedHeader>*</AllowedHeader>
    </CORSRule>
</CORSConfiguration>
```





