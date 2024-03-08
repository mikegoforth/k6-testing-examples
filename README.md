
# K6 Testing Examples

This repository contains a collection of scripts used for writing performance tests.




## Project Structure

```bash
\---k6-testing-examples
    |   script.js - Test that the K6 installation was successful.
    |
    \---tests
            browser.js - Runs a experimental browser test. For more details see below.
            load.js - Test with 10 virtual users with ramp up and ramp down stages @ 50 seconds.
            smoke.js - Test with a single VU @ 30 seconds.
```


## Resources

- 📖 [Getting Started](https://grafana.com/docs/k6/latest/get-started/) - Latest official Grafana K6 documentation.

- 🚧 [Browser Testing](https://grafana.com/docs/k6/latest/using-k6-browser/) - Documentation on browser testing. Currently experimental.

- 📺 [Udemy Course](https://www.udemy.com/course/k6-load-testing-performance-testing/) - A beginners course into performance testing in K6 led by [Valentin Despa](https://vdespa.com/)


## Usage/Examples

For built-in examples, please refer to the script definitions located in the package.json. Below is the example output of a successful smoke test.

```bash
$ npm run smoke

> k6@1.0.0 smoke
> k6 run ./tests/smoke.js


          /\      |‾‾| /‾‾/   /‾‾/
     /\  /  \     |  |/  /   /  /
    /  \/    \    |     (   /   ‾‾\
   /          \   |  |\  \ |  (‾)  |
  / __________ \  |__| \__\ \_____/ .io

     execution: local
        script: ./tests/smoke.js
        output: -

     scenarios: (100.00%) 1 scenario, 1 max VUs, 1m0s max duration (incl. graceful stop):
              * default: 1 looping VUs for 30s (gracefulStop: 30s)


     data_received..................: 88 kB  2.9 kB/s
     data_sent......................: 2.2 kB 72 B/s
     http_req_blocked...............: avg=9.51ms  min=0s     med=0s      max=171.19ms p(90)=0s      p(95)=25.67ms
     http_req_connecting............: avg=1.76ms  min=0s     med=0s      max=31.78ms  p(90)=0s      p(95)=4.76ms
     http_req_duration..............: avg=28.68ms min=26.6ms med=28.16ms max=34.71ms  p(90)=30.36ms p(95)=31.64ms
       { expected_response:true }...: avg=28.68ms min=26.6ms med=28.16ms max=34.71ms  p(90)=30.36ms p(95)=31.64ms
     http_req_failed................: 0.00%  ✓ 0        ✗ 18
     http_req_receiving.............: avg=65.9µs  min=0s     med=0s      max=685.2µs  p(90)=150.3µs p(95)=528.62µs
     http_req_sending...............: avg=0s      min=0s     med=0s      max=0s       p(90)=0s      p(95)=0s
     http_req_tls_handshaking.......: avg=3.13ms  min=0s     med=0s      max=56.5ms   p(90)=0s      p(95)=8.47ms
     http_req_waiting...............: avg=28.61ms min=26.6ms med=28.12ms max=34.71ms  p(90)=30.36ms p(95)=31.64ms
     http_reqs......................: 18     0.584178/s
     iteration_duration.............: avg=5.13s   min=5.09s  med=5.1s    max=5.28s    p(90)=5.19s   p(95)=5.24s
     iterations.....................: 6      0.194726/s
     vus............................: 1      min=1      max=1
     vus_max........................: 1      min=1      max=1

                                                                                                                                                                                                                                                                                         
running (0m30.8s), 0/1 VUs, 6 complete and 0 interrupted iterations                                                                                                                                                                                                                      
default ✓ [======================================] 1 VUs  30s                     
```