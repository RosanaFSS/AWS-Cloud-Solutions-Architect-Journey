<!DOCTYPE html>
<html>
<body>
  
<h1 align="center" style="font-family: 'Impact', sans-serif; color: white; font-size: 40px;">AWS Certified Solutions Architect - Associate, AWS SAA-C01</h1>
<br>

<div align="center">
  
|<h3>Design<br><code>Secure</code><br>Architectures</h3><p>Domain <code>1</code><br>30%</p>|<h3>Design<br><code>Resilient</code><br>Architectures</h3><p>Domain <code>2</code><br>26%</p>|<h3>Design<br><code>High-Performing</code><br>Architectures</h3><p>Domain <code>3</code><br>24%</p>|<h3>Design<br><code>Cost-Optimized</code><br>Architectures</h3><p>Domain <code>4</code><br>20%</p>|
|:---------------------------------:|:---------------------------------:|:---------------------------------:|:---------------------------------:|
|-----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|

</div>

<h1 align="center" style="font-family: 'Impact', sans-serif; color: white; font-size: 40px;">Domain 1</h1>


<br>

<h2><strong>Amazon Route 53</strong></h2>
<p>It is a highly available and scalable Domain Name System (DNS) web service. You can use Route 53 to perform 3 main functions in any combination: </p>

<ul style="list-style-type:square">
    <li>Register domain names</li>
    <li>DNS routing &nbsp; | &nbsp; route internet traffic to the resources for your domain</li>
    <li>Health checking &nbsp; | &nbsp; Check the health of your resources</li>
</ul></p>

<h2><strong>Amazon Route 53</strong> &nbsp; | &nbsp; Routing Policy</h2>

<p><ol type="1. ">
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-simple.html">Simple routing policy</a> &nbsp; | &nbsp; Use for a single resource that performs a given function for your domain, for example, a web server that serves content for the example.com website.<br> You can use simple routing policy for records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-failover.html">Failover routing policy</a> &nbsp; | &nbsp; Use when you want to configure active-passive failover.<br> You can use Failover routing policy for records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geo.html">Geolocation routing policy</a> &nbsp; | &nbsp; Use when you want to route traffic based on the location of your users.<br> You can use geolocation routing for records in both <code>public</code> and <code>private</code> hosted zones.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geoproximity.html">Geoproximity routing policy</a> &nbsp; | &nbsp; Use when you want to route traffic based on the location of your resources and, optionally, shift traffic from resources in one location to resources in another location. <br>You can use geoproximity routing to create records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-latency.html">Latency-based routing policy</a> &nbsp; | &nbsp; Use when you have resources in multiple AWS Regions and you want to route traffic to the Region that provides the best latency.<br>You can use latency routing policy for records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-ipbased.html">IP-based routing policy</a> &nbsp; | &nbsp; Use when you want to route traffic based on the location of your users, and have the IP addresses that the traffic originates from.<br>You <code>cannot</code> use IP-based routing policy for records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-multivalue.html">Multi value answer routing policy</a> &nbsp; | &nbsp; lets you configure Amazon Route 53 to return multiple values, such as IP addresses for your web servers, in response to DNS queries.<br>It's not a substitute for a load balancer, but the ability to return multiple health-checkable IP addresses is a way to use DNS to improve availability and load balancing.<br>You can use multivalue answer routing policy for records in a <code>private</code> hosted zone.<br><br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-weighted.html">Weighted routing policy</a> &nbsp; | &nbsp; lets you associate multiple resources with a single domain name (example.com) or subdomain name (acme.example.com) and choose how much traffic is routed to each resource.<br>You can use weighted routing policy for records in a  <code>private</code> hosted zone.</li>
</ol></p>


</body>
</html>

