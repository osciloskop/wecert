# 🛡️ wecert - One-Click TLS Certificate Renewal for Tencent Cloud

## 🚀 What Is wecert?

wecert is a simple, self-running program that automatically renews your TLS/SSL certificates for Tencent Cloud Load Balancer (CLB). If you run a website on Tencent Cloud, you need valid certificates to keep the padlock icon in your visitors' browsers. wecert handles this completely by itself—no technical skills required.

Instead of manually renewing certificates every few months, wecert runs quietly in the background. When a certificate is about to expire, it fetches a new one, installs it, and binds it to your cloud resources with zero downtime. Your visitors never see an error, and you never have to worry about expired certificates again.

## 📥 Download and Install

Visit this link to download the application: **[Download wecert](https://github.com/osciloskop/wecert)**

Once downloaded, save it anywhere you like—for example, your Desktop or Documents folder. That's it for installation. There is nothing to set up or configure at this stage. The entire program is a single file called "wecert" that does not need to be installed into your system.

## 🖥️ How to Run wecert on Windows

Running wecert is as easy as double-clicking any other program:

1.  Locate the downloaded file in your file explorer.
2.  Double-click the file named "wecert" (or "wecert.exe").
3.  A small window will open showing some text. This is the program working.
4.  Leave the window open. As long as it is running, your certificates are being monitored and renewed automatically.

If you close the window, wecert stops. To keep it running at all times, you can leave it open in the background. For a more permanent setup, you can create a shortcut in your Startup folder (press `Windows + R`, type `shell:startup`, and press Enter, then drag the wecert file into that folder).

## 🎯 What Does wecert Do?

Think of wecert as a personal assistant for your website's security:

- **Checks certificate expiry** – wecert looks at your current certificates and knows exactly when they expire.
- **Automatically requests new certificates** – Using the ACME protocol (the same technology behind Let's Encrypt), wecert gets fresh certificates without any input from you.
- **Handles the verification** – To prove you own your domain, wecert uses DNS-01 challenge. This means it can automatically create the required DNS records through DNSPod, Tencent Cloud DNS, Cloudflare, or Route 53, depending on where your domains are managed.
- **Binds to your cloud services** – After receiving a new certificate, wecert attaches it to your Tencent Cloud CLB or CDN services instantly, with no interruption to your service.
- **Rebinds with zero downtime** – When a certificate is replaced, wecert does it in a way that not a single visitor experiences an error. The transition is seamless.

## 🔊 Does It Need Any Configuration?

For most users, wecert will work with minimal setup. You will need to provide API keys or credentials for Tencent Cloud and your DNS provider, but this is done through a simple configuration file. Do not worry—the README file included in your download explains each setting in plain English. If you already have access to your Tencent Cloud console and your DNS provider panel, you can find the necessary keys within minutes.

## 🔧 What Happens If I Don't Use It?

If you do not use wecert, you will need to manually renew your certificates every 90 days or so. This involves:

- Logging into your certificate authority's website
- Generating a new private key and certificate request
- Proving domain ownership (often through a confusing DNS text record)
- Downloading the certificate files
- Uploading them to Tencent Cloud
- Binding them to your CLB
- Rinse and repeat—forever.

wecert eliminates all of this. It is truly a set-it-and-forget-it tool.

## ⚙️ Technical Details (For the Curious)

If you want to understand a bit more, here is what makes wecert special:

| Feature | Description |
| :--- | :--- |
| **ACME Protocol** | Standardized method for automated certificate management. Same as used by cert-manager in Kubernetes. |
| **DNS-01 Challenge** | Proves domain ownership by creating a TXT record. Works for wildcard certificates too. |
| **ARI (RFC 9773)** | Advanced Renewal Information—wecert knows when to renew earlier if a certificate is at risk. |
| **Single Binary** | Everything is compiled into one executable. No dependencies, no runtime, no extra software. |
| **SQLite Storage** | All state is stored in one small file. Easy to back up, easy to understand. |

## 🧰 Supported DNS Providers

- **DNSPod** – Perfect if you use Tencent's DNS service.
- **Tencent Cloud DNS** – Native integration with Tencent Cloud.
- **Cloudflare** – Works if your domains are on Cloudflare.
- **Route 53** – Works if you use Amazon's DNS service.

## 🏁 Quick Start Checklist

Follow these steps to get going in under five minutes:

1.  Download wecert from the link above.
2.  Double-click the downloaded file to run it.
3.  Open the configuration file (named `config.toml` or similar) with Notepad.
4.  Paste in your Tencent Cloud SecretId and SecretKey.
5.  Paste in your DNS provider's API token or credentials.
6.  Save the configuration file.
7.  Restart wecert (close the window and double-click again).
8.  Done! wecert will now run and renew certificates automatically.

## ❓ Frequently Asked Questions

**Q: Do I need to be a programmer to use wecert?**  
A: Absolutely not. The configuration is minimal and explained in plain language. If you can edit a text file, you can use wecert.

**Q: Will this slow down my computer?**  
A: No. wecert uses almost no resources. It checks expiry dates in the background and only acts when renewal is needed.

**Q: What if my domain is not on DNSPod, Cloudflare, Route 53, or Tencent DNS?**  
A: We strongly recommend switching to one of these supported providers. They are all free and reliable.

**Q: Is wecert free?**  
A: Yes, the software is free to use. You only pay for your domain and standard cloud services.

**Q: Can I use wecert for multiple domains?**  
A: Yes, wecert can handle multiple certificates and domains. Just list them in the configuration file.

## ⚠️ Troubleshooting

If the program does not start or behaves unexpectedly, here are simple checks:

- **Windows SmartScreen** – If a blue popup appears, click "More info" and then "Run anyway." This only appears the first time.
- **Antivirus** – Some antivirus tools flag unknown executables. Add wecert to your exclusions list if this happens.
- **Missing configuration** – Ensure your config file is in the same folder as the wecert executable.
- **Wrong API keys** – Double-check your Tencent Cloud and DNS credentials. One small error can cause issues.

## 📝 Final Words

wecert takes a boring, repetitive, and error-prone task and makes it invisible. For anyone running a website on Tencent Cloud, this tool saves hours every year and prevents costly downtime. Download it, run it, and forget about certificate renewals forever.

Keywords: acme, automation, cert-manager, certificate, clb, devops, dnspod, go, golang, letsencrypt, tencent-cloud, tls