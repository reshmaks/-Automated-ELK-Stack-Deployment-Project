## Identity and Access Management

This ELK web server runs on port `5601`. Create an incoming rule for your security group that allows TCP traffic over port `5601` from your IP address.

Verify that you can load the ELK stack server from your browser at `http://20.80.232.219:5601/app/kibana`.

Solutions:
Sending traffic to the entire ELK-NET is fine here because there are no other resources besides the ELK server.

![](Images/Security_group.png)

If everything is working correctly, you should see this webpage:

![](Images/Kibana_Home.png)


