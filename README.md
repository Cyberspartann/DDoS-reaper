# **DDoS-Reaper**

## **Overview**

This Python-based **Distributed Denial-of-Service (DDoS)** attack simulation script is designed to simulate a large-scale attack on a target web server by sending a massive volume of HTTP requests. The primary use case of this tool is for **network security professionals**, **developers**, and **system administrators** who need to assess the resilience of their servers and infrastructure under heavy load conditions. By mimicking DDoS attacks, the script can help identify vulnerabilities, test server capacity, and fine-tune defenses.

The script leverages the power of Python's `asyncio` and the `aiohttp` library to send HTTP requests asynchronously, which enables the tool to make many requests in parallel. This allows for a higher volume of traffic with much more efficiency compared to traditional synchronous HTTP requests. The attack is highly customizable and can be configured with various parameters such as request methods (**GET, POST, PUT, DELETE, etc.**), headers, request payloads, proxy rotation, and rate-limiting options. These settings give the user full control over the attack's behavior, allowing for both light and heavy load testing.

In addition to the ability to control various attack parameters, the script also features **IP spoofing** via randomized user-agents, making it more difficult for target servers to detect and block the requests. If proxies are provided, the tool can rotate between **SOCKS5 proxies** to further obscure the origin of the traffic.

## **Key Features**

- **Asynchronous HTTP Requests**: Uses `asyncio` and `aiohttp` for concurrent, high-volume requests.
- **Customizable Attack Settings**: Configure request methods, rate limits, custom headers, and payload data.
- **Proxy Rotation**: Mask the origin of requests by rotating between **SOCKS5 proxies**.
- **Randomized User-Agent Spoofing**: Each request is sent with a randomly chosen **user-agent** to mimic traffic from different devices.
- **Real-Time Logging**: Log **HTTP status codes** (200 OK, 400 Bad Request, etc.) for each request to track attack progress.
- **Educational Purpose**: Intended for **legal and ethical testing**, helping to identify performance bottlenecks or server vulnerabilities.

## **Requirements**

- **Python 3.7+**
- **Dependencies**:
  ```bash
  pip install aiohttp aiohttp_socks
  ```

## **Usage**

Run the script with the following command:

```bash
python3 ddos_attack.py <url> <num_tasks> --rate_limit <rate_limit> --method <method> --headers <headers> --data <data> --proxies <proxies>
```

### **Arguments:**

- `<url>`: **The target URL.**
- `<num_tasks>`: **Number of concurrent requests to send.**
- `--rate_limit <rate_limit>`: (**Optional**) **Limit the number of requests per second.**
- `--method <method>`: (**Optional**) **HTTP method to use (GET, POST, etc.).**
- `--headers <headers>`: (**Optional**) **Custom headers as JSON.**
- `--data <data>`: (**Optional**) **Request payload data.**
- `--proxies <proxies>`: (**Optional**) **List of SOCKS5 proxies to rotate.**

## **Example**

```bash
python3 ddos_attack.py https://example.com 1000 --rate_limit 10 --method GET --headers '{"User-Agent": "Mozilla/5.0"}' --proxies proxies.txt
```

## **Legal Disclaimer**

This tool is designed **strictly for educational and testing purposes only**. **Unauthorized use against a target without explicit permission is illegal** and punishable under cybercrime laws. The developers assume **no responsibility** for misuse of this tool.

## **License**

**MIT License.** See `LICENSE` file for more details.

---

**DDoS-Reaper** is a powerful tool for **stress testing your own infrastructure** and ensuring your systems are resilient against high-traffic scenarios. **Use responsibly and ethically!**

