# System-Design-Project-Designing-A-URL-Shortener
A URL shortener is a service that converts long urls into compact, easy to share aliases

# High level design of a URL shortener
We have to start by clarifying the requirements

# 1. What is the expected scale? How many new URLs per day and how many redirects?
# 2. What characters are allowed in the shortened URL?
# 3. Should users be able to specify custom aliases for their URLS?
# 4. Do the short URLs need to expire after a certain time?
# 5. Do we need analytics like click counts?

# 1.1 Functional Requirements
Shorten URL- Given a long URL, generate a unique short URL
Redirect- When a short URL is accessed, redirect the user to the original long URL.
Custom Aliases-Allow users to create custom short codes
Expiration- Support link expiration with default and custom TTLs
Analytics- Track basic click counts for each short URL

# 1.2 Non- Functional Requirements
High Availability
Scalability
Low latency- 50ms(p99)
Durability
Uniqueness- Each long URL should map to unique short URL

# 3. Core APIs
The URL shortener service needs a minimal but powerful set of APIs to create,manage and resolve shortened links.

# 3.1 Create a Short URL
Endpoint: POST /shorten
# 3.2 Redirect to Long URL
Endpoint: GET /{short_code}
# 3.3 Get URL Analytics
Endpoint : GET /analytics/{short_code}

# 4. High-Level Design
our system must satisfy two core requirements
