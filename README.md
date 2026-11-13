<div align="center">

# SRI VILLIAM SAI A

**I build Java backends and native iOS apps with SwiftUI, and work with AWS and Google&nbsp;Cloud.**

My projects include Spring Boot APIs, carbon tracking, and the iOS apps Glassora and Remolad.

<p>
  <img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?style=flat-square" />
  <img alt="Spring Boot" src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&amp;logo=springboot&amp;logoColor=white" />
  <img alt="Spring Cloud" src="https://img.shields.io/badge/Spring_Cloud-1C6D44?style=flat-square" />
  <img alt="MySQL" src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&amp;logo=mysql&amp;logoColor=white" />
  <img alt="Swift" src="https://img.shields.io/badge/Swift-F05138?style=flat-square&amp;logo=swift&amp;logoColor=white" />
  <img alt="AWS" src="https://img.shields.io/badge/AWS-232F3E?style=flat-square" />
  <img alt="Google Cloud" src="https://img.shields.io/badge/Google_Cloud-4285F4?style=flat-square&amp;logo=googlecloud&amp;logoColor=white" />
</p>

<p>
  <a href="https://www.linkedin.com/in/srivilliamsai/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&amp;logo=linkedin&amp;logoColor=white" /></a>
  <a href="https://srivilliamsai.vercel.app/"><img alt="Portfolio" src="https://img.shields.io/badge/Portfolio-24292F?style=for-the-badge" /></a>
  <a href="https://x.com/srivilliamsai"><img alt="X" src="https://img.shields.io/badge/X-000000?style=for-the-badge&amp;logo=x&amp;logoColor=white" /></a>
</p>

</div>

<table align="center">
  <thead>
    <tr>
      <th width="33%" scope="col" align="center">Hire</th>
      <th width="34%" scope="col" align="center">Contribute</th>
      <th width="33%" scope="col" align="center">Reach out</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td align="center" valign="top">Java backends and native iOS apps.</td>
      <td align="center" valign="top">Report bugs or suggest improvements.</td>
      <td align="center" valign="top">Discuss backend, iOS, or cloud work.</td>
    </tr>
    <tr>
      <td align="center" valign="top"><a href="https://www.linkedin.com/in/srivilliamsai/">LinkedIn</a></td>
      <td align="center" valign="top"><a href="https://github.com/srivilliamsai/CRM_Application/issues" title="CRM issues">CRM</a> · <a href="https://github.com/srivilliamsai/pitstop-backend/issues" title="PitStop issues">PitStop</a></td>
      <td align="center" valign="top"><a href="https://srivilliamsai.vercel.app/">Portfolio</a></td>
    </tr>
  </tbody>
</table>

<div align="center">

| CRM | Carbon Footprint | PitStop |
|:---:|:---:|:---:|
| Lookup HTTP 200 | Log saved and read | Order saved and listed |
| [Gateway test](case-studies/crm-application.md#try-it-locally) | [Storage tests](case-studies/carbon-footprint.md#try-it-locally) | [API tests](case-studies/pitstop.md#try-it-locally) |

<sub>Results from local API smoke tests. The linked case studies show the requests and setup.</sub>

</div>

## 1. CRM Application

A React dashboard backed by Spring Boot services for customer records, leads, and sales activity. I built the customer API and traced how Spring Cloud Gateway resolves it by service name through Eureka.

<table>
<tr>
<td width="50%" valign="top">

[**CRM Application**](https://github.com/srivilliamsai/CRM_Application) · [Case study](case-studies/crm-application.md)

**Local checks**

- Create a customer through the gateway → HTTP 201
- List customers by company → HTTP 200 with the saved record

</td>
<td width="50%" valign="top">

**Request path**

```mermaid
flowchart TD
    Request["Customer lookup"] --> Gateway["Gateway"]
    Gateway -.-> Eureka["Eureka"]
    Gateway --> Customer["Customer service"]
    Customer --> MySQL["MySQL"]
```

<sub>The auth service validates JWTs for its protected endpoints. The customer lookup uses the company ID as a query filter.</sub>

</td>
</tr>
</table>

## 2. Carbon Personal Footprint App

A React dashboard and Spring Boot API for recording the footprint of transport, diet, and energy use. I built the dashboard and API as part of my Infosys internship project.

<table>
<tr>
<td width="50%" valign="top">

**Request path**

```mermaid
flowchart TD
    Dashboard["React dashboard"] --> Logs["Carbon log API"]
    Logs --> Calculation["Calculate total"]
    Calculation --> MySQL["Save to MySQL"]
```

<sub>The separate emission-factor endpoint caches its simulated lookup in Redis.</sub>

</td>
<td width="50%" valign="top">

[**Carbon Personal Footprint App**](https://github.com/srivilliamsai/CarbonPersonalFootprintApp) · [Case study](case-studies/carbon-footprint.md)

**Local checks**

- Submit a log with a bearer token → history returned the saved record
- Look up an emission factor → Redis held the cache key

</td>
</tr>
</table>

## 3. PitStop

A roadside-assistance project with Flutter screens for exploring services and Spring Boot modules for orders and emergency reports.

<table>
<tr>
<td width="50%" valign="top">

[**Flutter**](https://github.com/srivilliamsai/pitstop) · [**Backend**](https://github.com/srivilliamsai/pitstop-backend) · [Case study](case-studies/pitstop.md)

**Direct API checks**

- Create and list a fuel order → the new order appeared as pending
- Query emergency reports by severity → HTTP 200 with authentication

</td>
<td width="50%" valign="top">

**Service boundaries**

```mermaid
flowchart TD
    Routes["Gateway routes"]
    Routes -.-> Orders["Order service"]
    Routes -.-> Emergency["Emergency service"]
```

<sub>Direct service checks passed. The gateway returned HTTP 503.</sub>

</td>
</tr>
</table>

## 4. Swift and iOS development

**Remolad.** One of my native iOS projects.

**Glassora.** I built and published a SwiftUI wallpaper app with category browsing, previews, and favorites. [App Store](https://apps.apple.com/in/app/glassora-wallpapers-hd-4k/id6777764126) · [Launch write-up](https://dev.to/srivilliamsai/i-just-launched-my-first-ios-app-after-16-days-in-app-review-f5b)

## 5. AWS and Google Cloud

**AWS.** I host my portfolio on AWS Amplify and run its assistant backend on AWS Lambda. [Deployment notes](https://github.com/srivilliamsai/portfolio/blob/main/docs/AMPLIFY_RELEASE.md)

**Google Cloud and Firebase.** I work with Google Cloud and use Firebase to manage Glassora’s wallpaper catalog. [Glassora case study](https://main.d229cwpntq8yz1.amplifyapp.com/glassora)

## Writing and background

**Writing.** I wrote about using Kafka events to verify activities and regenerate a resume in a Node.js microservices project. [Project architecture](https://github.com/srivilliamsai/resume-ecosystem-node#%EF%B8%8F-architecture) · [DEV Community article (JSON)](https://dev.to/api/articles/3406775)

**Background.** My Infosys internship project included building the Spring Boot API and React dashboard for the carbon footprint tracker. [Internship project](case-studies/carbon-footprint.md)

<div align="center">

`Java` `Spring Boot` `Spring Cloud` `MySQL` `Redis` `Kafka` `React` `Flutter` `Swift` `SwiftUI` `iOS` `AWS` `Google Cloud` `Firebase`

</div>
