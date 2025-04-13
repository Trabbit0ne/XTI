# Cross-Title Injection (XTI)

<img src="https://github.com/user-attachments/assets/b84daf4b-18dd-4580-965b-1930f81899fd" alt="image">

## Introduction
Cross-Title Injection (XTI) — formerly referred to as “XSS end title” — is a technique that enables attackers to bypass traditional XSS protections by injecting malicious scripts into the `<title>` tag of a web page. By exploiting unsanitized user input, this method triggers the execution of harmful code during the page rendering phase. XTI introduces serious security threats, including phishing attacks, session hijacking, and malware distribution, highlighting the critical need for robust input validation and secure content handling practices.

## Overview
This repository aims to educate developers and security professionals about XTI, its implications, and how to mitigate it effectively.

## Table of Contents
- [Examples](#examples)
- [Payloads](#payloads)
- [Proof of Concept](#proof-of-concept)
- [Mitigation Strategies](#mitigation-strategies)
- [Further Reading](#further-reading)
- [Contributing](#contributing)

## Examples
Here are some scenarios where XTI can be exploited:
1. **E-commerce Platforms**: Malicious titles in product listings can execute harmful scripts when users view the page.
2. **Content Management Systems**: Users can inject scripts into post titles that execute when others view the post.
3. **Social Media**: Custom profile titles may be manipulated to run scripts on other users' browsers.

## Payloads
Below are sample payloads that demonstrate XTI in action. These are for educational purposes only:

```html
</title><img src=x onerror=alert('XTI')>
```

```html
</title><script>alert('XTI bypass');</script>
```

```html
</title><svg/onload=confirm('XTI')>
```

> **Note**: Some browsers may sanitize the `<title>` tag contents more strictly than others. Testing across multiple engines is recommended.

## Proof of Concept
You can find a demonstration of a successful XTI attack in the following video or GIF:

### 📽️ MP4 / GIF PoC
> Embed your video or GIF here:
```markdown
![XTI PoC](https://yourdomain.com/xti-poc.gif)
```
Or:
```html
<video width="640" height="360" controls>
  <source src="https://yourdomain.com/xti-demo.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

## Mitigation Strategies
To protect against XTI vulnerabilities, consider the following strategies:
- **Input Validation**: Ensure that all user input is sanitized and validated.
- **Output Encoding**: Use proper encoding techniques to prevent script execution.
- **Content Security Policy (CSP)**: Implement CSP headers to restrict script sources.
- **Regular Security Audits**: Conduct regular assessments to identify and fix vulnerabilities.

## Further Reading
- [Understanding Cross-Title Injection (XTI)](https://emiledurand.medium.com/cross-title-injection-xti-a-new-xss-bypass-you-should-know-b1fb6272a879)

## Contributing
Contributions are welcome! Please feel free to submit issues or pull requests to help improve this repository.
