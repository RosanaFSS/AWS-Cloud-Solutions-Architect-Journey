<h1 align="center" style="font-family: 'Impact', sans-serif; color: white; font-size: 40px;">AWS Certified Solutions Architect - Associate, AWS SAA-C01</h1>
<br>

<div align="center">
  
|<h3>Design<br><code>Secure</code><br>Architectures</h3><p>Domain <code>1</code><br>30%</p>|<h3>Design<br><code>Resilient</code><br>Architectures</h3><p>Domain <code>2</code><br>26%</p>|<h3>Design<br><code>High-Performing</code><br>Architectures</h3><p>Domain <code>3</code><br>24%</p>|<h3>Design<br><code>Cost-Optimized</code><br>Architectures</h3><p>Domain <code>4</code><br>20%</p>|
|:---------------------------------:|:---------------------------------:|:---------------------------------:|:---------------------------------:|
|-----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|

</div>

<h1 align="center" style="font-family: 'Impact', sans-serif; color: white; font-size: 40px;">Domain 1</h1>


<br>

<h2><code>Amazon Route 53</code> Routing Policy</h2>

<p><ol type="1. ">
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-simple.html">Simple routing policy</a> : lets you route traffic to a single resource, for example, to a web server for your website.<br> You can use simple routing policy for records in a <code>private</code> hosted zone.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-failover.html">Failover routing</a> :  lets you route traffic to a resource when the resource is healthy or to a different resource when the first resource is unhealthy.<br> You can use simple routing policy for records in a <code>private</code> hosted zone.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geo.html">Geolocation routing</a> :  lets you choose the resources that serve your traffic based on the geographic location of your users, meaning the location that DNS queries originate from. For example, you might want all queries from Europe to be routed to an Elastic Load Balancing load balancer in the Frankfurt Region.<br> You can use geolocation routing for records in both <code>public</code> and <code>private</code> hosted zones.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-geoproximity.html">Geoproximity routing</a> :   lets Amazon Route 53 route traffic to your resources based on the geographic location of your users and your resources. It routes traffic to the closest resource that is available. You can also optionally choose to route more traffic or less traffic to a given resource by specifying a value, known as a bias. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-latency.html">Latency-based routing</a> : If your application is hosted in multiple AWS Regions, you can improve performance for your users by serving their requests from the AWS Region that provides the lowest latency.<br> Latency-based routing is based on latency measurements taken over a period of time, and the measurements reflect these changes.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-latency.html">Latency-based routing</a> : If your application is hosted in multiple AWS Regions, you can improve performance for your users by serving their requests from the AWS Region that provides the lowest latency.<br> Latency-based routing is based on latency measurements taken over a period of time, and the measurements reflect these changes.<br>You can use latency routing policy for records in a <code>private</code> hosted zone.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-multivalue.html">Multi value answer routing</a> :  lets you configure Amazon Route 53 to return multiple values, such as IP addresses for your web servers, in response to DNS queries.<br>It's not a substitute for a load balancer, but the ability to return multiple health-checkable IP addresses is a way to use DNS to improve availability and load balancing.<br>You can use multivalue answer routing policy for records in a <code>private</code> hosted zone.<br></li>
    <li><a href="https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/routing-policy-weighted.html">Multi value answer routing</a> : lets you associate multiple resources with a single domain name (example.com) or subdomain name (acme.example.com) and choose how much traffic is routed to each resource.<br>You can use weighted routing policy for records in a  <code>private</code> hosted zone.</li>
  Geoproximity routing
</ol></p>

