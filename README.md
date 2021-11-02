Deployment process


1. Apply local changes to proxy, server or front
	a. Pull / Push changes to github on master
    b. In the folder docker build . -t <proxy, server or front>
    c. “docker tag <proxy, server or front> gtertrais/<proxy, server or front>”
    d. “docker push gtertrais/<proxy, server or front>”

2 Connect to remote aws EC2 : 
	a. Go in the directory with registered .pem key
	b. Run “ssh -i test3.pem ubuntu@18.222.106.3” (public IPV4 aws instance)

3. Once connected on remote: 
	a. Go in docker folder: “cd docker-compose”
	b. Update docker-compose: “git pull”
	c. Run the alias “docker-update” or:
		i. 		stop images: “docker-compose stop”,
		ii. 	remove images: “docker-compose rm -f“
		iii. 	update images:  “docker-compose pull”
		iv.		run images: “docker-compose up -d”
	d. Verify on the website the changes has been accepted
