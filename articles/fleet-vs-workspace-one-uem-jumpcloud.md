## Overview

Fleet is an open-source, multi-platform device management solution supporting macOS, Windows, Linux, ChromeOS, iOS, iPadOS, and Android. Fleet combines MDM capabilities and osquery for near real-time device visibility, letting IT and security teams understand device state within seconds rather than hours. Fleet supports GitOps workflows and offers flexible deployment options including a fully cloud-managed server instance or self-hosting. Organizations like Stripe, Dropbox, and Fastly use Fleet to manage over 2 million devices globally.

VMware Workspace ONE UEM (now under Omnissa branding) is a cloud-based Unified Endpoint Management (UEM) solution supporting Windows, macOS, Linux, iOS, iPadOS, Android, and ChromeOS. Additional components like Workspace ONE Intelligence and Unified Access Gateway require separate licensing.

JumpCloud launched in 2012 as a cloud-based directory service, adding endpoint management capabilities over time rather than building as a purpose-built MDM. JumpCloud supports Windows, Apple, and Linux devices. JumpCloud is cloud-only with no self-hosting option.

## Key differences

| Attribute | Fleet | Workspace ONE UEM | JumpCloud |
| --- | --- | --- | --- |
| **Platform support** | macOS, iOS, iPadOS, Windows, Linux, ChromeOS, Android | Windows, macOS, Linux, iOS, iPadOS, Android, ChromeOS | Windows, macOS, Linux, iOS |
| **Deployment model** | Self-hosted or Fleet managed cloud | SaaS and on-premises deployment options (depending on edition) | Cloud-only |
| **GitOps support** | Native GitOps workflows for policies and configuration | Possible via APIs/automation; not a native GitOps workflow | Possible via APIs/automation; not a native GitOps workflow |
| **Device visibility speed** | Near real-time reporting via osquery | Agent/MDM check-in and event-based reporting (cadence configurable) | Agent check-in-based reporting (cadence configurable) |
| **Configuration verification** | Reports and policies verify observed device state via osquery | Compliance engine evaluates devices against configured rules | Agent reports and compares device state to configured policies |
| **Vulnerability management** | Built-in vulnerability detection for installed software (with sources such as NVD/KEV/EPSS); optional custom detections (for example, with YARA) | Patch management and vulnerability/compliance reporting (feature availability varies by module/licensing) | Software inventory and patch management with reporting (feature availability varies by plan) |
| **Compliance frameworks** | Prebuilt benchmark-aligned policies (for example, CIS) plus customizable policies and reporting | Policy-based compliance checks and reporting | Policy-based compliance checks and reporting |
| **File integrity monitoring** | Available (Fleet Premium) | Typically via additional products or integrations | Not a core feature |
| **Workflow integrations** | Webhooks for Jira, Zendesk, Tines, Okta Workflows, Slack | APIs and console-based workflows/integrations (some via add-ons) | APIs and directory-based integrations |
| **Security approach** | osquery-based visibility, vulnerability detection, and incident response workflows | Compliance, configuration, and access controls across endpoints | Directory-centric identity/device controls with endpoint management |

## Device management workflow comparisons

### Enrollment and provisioning

Fleet provides flexible device enrollment with MDM capabilities across all supported platforms. If you're migrating from an existing MDM, Fleet's end user migration feature allows devices to be easily migrated with straightforward and minimal end user interaction. Fleet is fully compatible with Apple's Managed Device Migration framework and can automatically migrate Windows devices that are MDM enrolled in any management solution.

Both Fleet and Workspace ONE UEM support zero-touch provisioning and automated enrollment. JumpCloud supports enrollment across Windows, macOS, and Linux devices.

### Configuration management

When a new security configuration needs to roll out across thousands of devices, configuration management determines how quickly and reliably that change happens.

Fleet manages device configuration through Fleets and Labels for organizing devices, and Configuration Profiles for applying settings across device groups. Fleet supports Apple’s MDM protocol and Declarative Device Management (DDM) for macOS, iOS, and iPadOS. Fleet is built on osquery. The [Fleetosqueryschema](https://fleetdm.com/tables/account_policy_data) has more than 300 data tables letting your IT team collect detailed device data to verify configuration compliance within seconds. Fleet's GitOps support lets your team manage device configurations as code. By integrating Fleet with a git repository, teams can store configuration profiles and policies in version control with audit trails and the ability to roll back changes.

Workspace ONE UEM manages configuration through Smart Groups, which target devices based on criteria like device type, operating system, user group, or custom attributes. Freestyle Orchestrator provides a visual interface for building multi-step workflows. Workspace ONE also supports script execution.

JumpCloud manages configuration through policies applied to individual devices, device groups, or entire fleets. JumpCloud supports custom scripts in Bash, PowerShell, or Python for configuration tasks.

### Software management

Fleet provides software management through Fleet-maintained apps, custom package uploads, Apple Apps and Books (VPP) distribution for volume purchasing and App Stores. Fleet Desktop offers self-service application installation, letting end users install approved software without IT intervention.

Workspace ONE UEM and JumpCloud also provide software distribution and patch management. Fleet differentiates with programmable automation through reports and API integrations that let organizations build custom deployment workflows. All three solutions can be integrated with [Munki](https://www.munki.org/munki/).

### Security and compliance

Fleet uses osquery to provide near real-time visibility, letting your security team query device state across your entire fleet within seconds. Fleet includes vulnerability detection as a built-in capability, and custom reports can check encryption status, identify unauthorized software, and assess overall security posture. For threat detection, Fleet supports YARA rules for custom indicators of compromise.

Fleet includes file integrity monitoring, scope transparency for end-users, and incident response capabilities in the core product. Fleet’s open-source codebase lets your security team audit exactly what's running on your devices.

Workspace ONE UEM provides a compliance engine that evaluates devices against configurable rules including passcode requirements, app blocklists, and encryption status. Non-compliant devices can be blocked from corporate resources. Both the JumpCloud and Workspace ONE codebases are proprietary and can't be inspected. JumpCloud provides conditional access policies that control access based on user identity, device trust, and network location.

### API and integration capabilities

API capabilities determine what's possible when your security team needs to automatically create a Jira ticket for every device with an unpatched vulnerability, or your compliance team wants vulnerability data flowing into Snowflake for reporting.

Fleet provides a REST API with programmatic access to all device data and management functions. Data exports to SIEM and analytics tools like Snowflake, Splunk, Elastic, and SumoLogic, while webhooks connect to Jira, Zendesk, Tines, Okta Workflows, and Slack. Fleet's open-source codebase lets your team inspect and extend API behavior.

Workspace ONE UEM provides REST APIs organized into sections for mobile applications, mobile device management, and system administration. APIs support OAuth 2.0 and Basic authentication.

JumpCloud provides REST APIs for managing users, devices, groups, and directory services. A PowerShell module is available for scripting common administrative tasks.

## Pricing and licensing

All Fleet products are open source. Fleet Free is free to use and can be self-hosted. Fleet Premium has more features and includes enterprise support, and it can be self-hosted or fully managed by Fleet in the cloud for you (a minimum of 700 devices is required to qualify for Fleet-managed cloud.) [Community support](https://fleetdm.com/support) is available for free in the public channels Fleet monitors. Per-device pricing is available for organizations of all sizes.

VMware Workspace ONE UEM uses a tiered SaaS licensing model with options including UEM Essentials, Desktop Essentials, and Mobile Essentials. Enterprise deployments typically require custom pricing with potential add-ons for features like Intelligence and Unified Access Gateway.

JumpCloud uses per-user pricing tiers for its products, including device management. Both Fleet and JumpCloud offer entry-level options for smaller organizations.

Verify current pricing directly with each vendor, as structures change over time.

## Open-source multi-platform device management

Organizations searching for the best MDM for Windows, Mac, and Linux environments often find that proprietary tools force trade-offs between platform coverage, visibility speed, and deployment flexibility. Fleet offers multi-platform management with complete source code transparency and the option to self-host for complete data control.

Fleet combines MDM capabilities with osquery-based reports across 300+ data tables, letting your team see device state in seconds rather than hours. Companies like Stripe have consolidated multiple device management tools onto Fleet for unified multi-platform visibility. [Schedule a demo](https://fleetdm.com/demo) to see how Fleet fits your multi-platform device management needs.

## Frequently asked questions

### What's the main difference between open-source device management and traditional UEM?

Open-source device management provides source code transparency, letting your team audit exactly what's running on your devices. Traditional UEM products are proprietary, meaning you can't verify how they collect data or enforce configurations. 

### How does device reporting speed affect security operations?

Near real-time reporting lets your security team detect and respond to threats significantly faster than products with hourly or daily check-in intervals. When a vulnerability is disclosed, you can query your entire fleet to identify affected devices within seconds rather than waiting for the next scheduled sync. This rapid visibility is critical for incident response, compliance verification, and security audits.

### What is self-hosting?

Self-hosting gives your organization complete data sovereignty and network isolation, which is particularly valuable if you have strict compliance requirements or air-gapped environments. Most traditional UEM products operate primarily as cloud services with limited on-premises options. JumpCloud is cloud-only with no self-hosting option. If your organization requires self-hosting and data sovereignty, evaluate the best [mdm solutions](https://fleetdm.com/docs/deploy/deploy-fleet) for Windows, Linux, and Mac that support full on-premises deployment.

### How long does it take to migrate from an existing device management tool?

Implementation and migration timelines vary based on fleet size and organizational requirements. The best MDM solutions now offer migration features that let devices transition with minimal or no end-user action or device re-enrollment. Organizations typically complete pilot deployments within days and can scale to full fleet migration over weeks depending on change management processes. Fleet's MDM migration capabilities simplify the switch from legacy tools. [Schedule a demo](https://fleetdm.com/demo) with Fleet to discuss specific implementation timelines and migration strategies for your environment.

<meta name="articleTitle" value="What's the best MDM for Windows, Mac, and Linux in 2026?">
<meta name="authorFullName" value="Brock Walters">
<meta name="authorGitHubUsername" value="nonpunctual">
<meta name="category" value="articles">
<meta name="publishedOn" value="2026-03-17">
<meta name="description" value="Compare Fleet, Workspace ONE UEM, and JumpCloud for multi-platform device management. See which MDM offers the best visibility, GitOps, and APIs.">
