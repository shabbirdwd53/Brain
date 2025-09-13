
#linkedIn #springboot 


Most developers know what API Rate Limiting is, but few actually implement it from scratch.

This week, I built a basic rate limiter in Spring Boot, and here’s how you can do it step by step.

If you're building public APIs or internal services, this is one of the easiest ways to protect your system from overuse.

Let’s break it down.

Step 1: Identify the key to rate limit  
This could be based on IP address, API key, or user ID.

`String key = request.getRemoteAddr();`


Step 2: Track requests using a map  
Use a thread-safe map to store request data per key.

`Map<String, RequestInfo> requestMap = new ConcurrentHashMap<>();`



Step 3: Create a filter  
Check each request before it reaches the controller.

`public class RateLimitFilter extends OncePerRequestFilter {     
@Override     
protected void doFilterInternal(...) {         
// logic goes here     } }`


Step 4: Define your rule  
Allow a certain number of requests per time window.

`if (requestCount >= 10 && withinOneMinute(lastRequestTime)) {     response.setStatus(429);     
return; }`


Step 5: Register the filter  
So it’s applied to all requests.

`@Bean public FilterRegistrationBean<RateLimitFilter> rateLimitFilter() {     return new FilterRegistrationBean<>(new RateLimitFilter()); }`


This is a simple in-memory solution and works well for learning or small apps.

For production, consider Redis for distributed rate limiting or use an API Gateway like Kong or Spring Cloud Gateway.

Understanding how it works internally gives you more flexibility and better control over your system behavior.

If you'd like me to share the complete code, just let me know in the comments.

Keep building. Keep learning.