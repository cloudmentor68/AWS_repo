# create linux-ec2-instance and host a webapp

AMI = al2023-ami-2023.9.20251117.1-kernel-6.1-x86_64

INSTANCE TYPES = t3.micro

KEYPAIR = anyname.ppk

SECURITY GROUPS = ssh, alltraffic(anywhere)

AUTO ASSIGN PUBLIC-IP (ENABLE)


## 1. Login into your EC2 instance

Login as : `ec2-user`

```
sudo yum update -y
sudo yum install httpd -y
```

## 2. Start  Apache & Enable on boot

```
sudo systemctl start httpd
sudo systemctl enable httpd
```

## 3. check status

```
sudo systemctl status httpd
```

## 4. Create your webapp file for host a webapp

```
<html>
<head>
<body>
<title> CLOUDLAPTOP </title>
<h1> WELCOME TO CLOUDLAPTOP </h1>
<h2> aws azure gcp & other clouds </h2>
<h1> connect with us! thank you </h1>
</body>
</head>
</html>
```

copy above code & paste it inside that `index.html` file

```
sudo nano /var/www/html/index.html
```

ctrl+x , press-y , enter



## 5. Allow permissions

```
sudo chown apache:apache /var/www/html/index.html

sudo chmod 644 /var/www/html/index.html
```

## 6. copy and paste instance public ip in your broswer and access your webapp

`NB: Remove s from (http)`
