# DNS-Hijack

**DNS-Hijack** enables you to route all internet traffic from devices that don't support proxy settings (like smart TVs or game consoles) through a SOCKS5 proxy, without modifying the devices themselves.

---

## 🛠️ How It Works

1. **DNS Redirection**: A custom DNS server responds to all domain queries with a specified IP address, directing all traffic to a single server.

2. **Traffic Interception**: The server at that IP address runs HTTP and HTTPS forwarders that inspect incoming requests to determine their intended destinations.

3. **Proxy Forwarding**: The forwarders then route the traffic to the actual target servers via a SOCKS5 proxy.

---

## 📦 Components

* **DNS Server**: Answers all DNS queries with the specified IP address.
* **HTTP Forwarder**: Handles HTTP traffic, determining the target server from the `Host` header.
* **HTTPS Forwarder**: Handles HTTPS traffic, extracting the target server from the TLS SNI (Server Name Indication).

---

## 🚀 Getting Started

### Prerequisites

* **Go**: Ensure Go is installed on your system. [Install Go](https://golang.org/doc/install)
* **SOCKS5 Proxy**: Have access to a SOCKS5 proxy server.

### Installation

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Kimya-M/DNS-Hijack.git
   cd DNS-Hijack
   ```

2. **Build the Application**:

   ```bash
   go build
   ```

   This will generate an executable named `DNS-Hijack`.

### Running the Application

Run the application with the IP address that should be returned for all DNS queries:

```bash
./DNS-Hijack <redirect_ip>
```

Replace `<redirect_ip>` with the IP address of the server running the HTTP and HTTPS forwarders.
