# A/B Testing using F5 DeviceID and NGINX+

I recently figured out how to use F5's DeviceID service with NGINX+ to perform A/B testing.
This is not only a cool and geeky thing to do, but I figured out it's very very useful.
Along the way, I also wrote a crude control panel page to let me change the split without resorting to curl :)

## What is this?

This post is about an amalgam of several things.

1. A/B testing with NGINX+
2. Using the split_clients directive in NGINX+ to split traffic.
3. Controlling the split of traffic based on a dynamically updatable key value pair in NGINX+.
4. Using DeviceID as the mechanism for splitting the traffic (this means each device or browser instance).

## Why would I do this? (A lightbulb moment)
I had been looking at ways to use DeviceID with NGINX since it was released late last year.
The intention was to use it in a way that was not strictly a security related use case, but to use it in such way and for a purpose where I needed to have a fine grained view of a client identifier.

I thought to myself - "When I do A/B testing or canary testing, I have a need to identify the client to be able to split traffic"

**A LIGHTBULB WENT OFF**

I could use the deviceID as a unique identifier for identifying clients but also for directing the clients' to new versions of my application deployment.

## Built on the shoulders of giants

Like a lot of open source ideas, this is built on the shoulders of giants.
Specifically, two NGINX blogs that I have to mention.

Kevin Jones' excellent blog: https://www.nginx.com/blog/performing-a-b-testing-nginx-plus/

and

Rick Nelson's excellent blog: https://www.nginx.com/blog/dynamic-a-b-testing-with-nginx-plus/


## NGINX+ 

NGINX+ has a few key abilities that I'm going to use. 

I'm going to split clients' based on a variable.
I'm going to keep an in memory map of client to application.
I'm going to dynamically update the split values as a percentage.

### Split

The split functionality of NGINX is provided by the [split_clients](https://nginx.org/en/docs/http/ngx_http_split_clients_module.html) module.

### Key value pair

### Testing

### Dynamically update the split

## Vue control page

## DeviceID

### Why this is important

### What it gives me

## What's next?

