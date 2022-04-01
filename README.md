# bws-demo-scripts

### SLC folter-title function

```ts
exports.handler = async (event) => {
  const toKebabCase = str =>
	str && str
	.match(/[A-Z]{2,}(?=[A-Z][a-z]+[0-9]*|\b)|[A-Z]?[a-z]+[0-9]*|[A-Z]|[0-9]+/g)
	.map(x => x.toLowerCase())
	.join('-');
 
  const response = toKebabCase(event.string);
  
  return response;
};
```

### SC initial script

```bash
#!/bin/bash
# Use this for your user data (script from top to bottom)
# install httpd (Linux 2 version)
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
sudo chown -R ec2-user:ec2-user /var/www/html
sudo chmod -R 755 /var/www/html
```
