# Performance Comparison Between Multithreaded, Singlethreaded, TreadPool Web Servers

This project explores the performance impacts of multithreading strategies in Java, specifically comparing single-threaded, multithreaded, and thread pool approaches under varying client load using apache-jmeter.
## Analysis

- Single-Threaded Approach:
    * Processes each client request sequentially.
    * Fails/Waits the incoming threads as another thread has already taken up cpu space 
- Multithreaded Approach:
    * Spawns a new thread for each client request.
    * better than single-threaded but still has busy waiting.
- Thread Pool Approach:
    * Utilizes a fixed-size thread pool to manage client requests efficiently.
    * a set of 10 pool size of threads are being reused 
    * when a thread becomes free, then the incoming threads are allocated to one of the 10 threads
    * better effiency than Multithreaded and Single-Threaded results


## Comparison

- Single-Threaded
    * `60K requests in 60 seconds`
    * `high deviation is observed`
![60K in 1min](https://github.com/Broilzzz/MultiThreaded-ThreadPool-SingleThreaded-Web-Server-/assets/123230400/7f12a34e-3a68-4561-b247-7d15a984d456)

- Multithreaded
    * `60K requests in 60 seconds`
    * `comparatively lower deviation than Single-Threaded`

![60k multi](https://github.com/Broilzzz/MultiThreaded-ThreadPool-SingleThreaded-Web-Server-/assets/123230400/3148fd8f-c3cf-4540-82fd-987a75910134)

- Thread Pool
    * `600K requests in 60 seconds`
    * `best performance when compared to Multithreaded and      Single-Threaded`
![600k pool](https://github.com/Broilzzz/MultiThreaded-ThreadPool-SingleThreaded-Web-Server-/assets/123230400/bfffda8d-dd74-4e61-94b1-f032de480c7b)

## Run the Project Locally

- Clone the project

```bash
  git clone https://github.com/Broilzzz/MultiThreaded-ThreadPool-SingleThreaded-Web-Server.git
```

- Go to the project directory

```bash
  cd MultiThreaded-ThreadPool-SingleThreaded-Web-Server
```


- Run the Project using terminal
- Open Apache JMeter to run you own tests
