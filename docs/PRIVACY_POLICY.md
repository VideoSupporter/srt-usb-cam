# Privacy Policy for SRT USB CAM

**Last Updated: May 9, 2026**

## Introduction

This Privacy Policy describes how SRT USB CAM ("we", "our", or "the application") handles user information. We are committed to protecting your privacy and being transparent about the application's data practices.

## Information Collection

**SRT USB CAM does not collect, transmit, or store personal information for analytics, tracking, advertising, or profiling.**

The application operates on your local computer and does not:

- Collect personal data
- Track user behavior
- Send analytics or telemetry data
- Connect to our servers for data collection
- Share information with third parties

## Local Data Storage

SRT USB CAM may store the following data locally on your computer:

### Application Settings

- Last selected camera identifier
- Destination IP address and port
- Automatic reconnection setting
- Window position or UI state, when supported

### Logs

- Application start and stop events
- Camera selection and input format results
- SRT connection, disconnection, and reconnection events
- Transmission start and stop events
- Error details needed for troubleshooting

This data is stored locally on your device and is not sent to us.

## Camera and Video Data

The application accesses the USB camera selected by the user and uses the camera video to create an MPEG-TS/H.264 stream.

- Camera video is transmitted only to the SRT destination configured by the user.
- The application does not upload camera video to our servers.
- The application does not record video by itself unless a receiver or external tool saves the stream.
- Users are responsible for the destination address and for handling video according to their organization or local requirements.

## Network Activity

SRT USB CAM sends video by:

- Connecting to a user-configured SRT receiver in caller mode
- Sending MPEG-TS/H.264 video over SRT

The application only communicates with the destination IP address and port configured by the user for SRT transmission.
No analytics, advertising, or tracking network connections are made by the application.

## Third-Party Services

SRT USB CAM does not integrate with or use third-party analytics, tracking, or advertising services.

The application uses third-party software components for its functionality, including SRT-related libraries and Windows platform components. These components are used locally as part of the application.

## Data Security

Since settings and logs are stored locally on your computer:

- You are responsible for the security of your device.
- Use firewall and network settings appropriate for your environment.
- Treat transmitted camera video as sensitive when it contains private or confidential content.

The current version does not enable SRT encryption by default.

## Children's Privacy

SRT USB CAM does not knowingly collect any information from anyone, including children under the age of 13.

## Changes to This Privacy Policy

We may update this Privacy Policy from time to time. Any changes will be reflected in the application documentation with an updated "Last Updated" date.

## Contact Information

If you have questions about this Privacy Policy, please:

- Open an issue on our [GitHub repository](https://github.com/VideoSupporter/srt-usb-cam/issues)
- Contact us at: videosp.info@gmail.com

## Your Rights

As SRT USB CAM does not collect personal information, there is no personal data held by us to:

- Request access to
- Request deletion of
- Request correction of
- Request transfer of

Local application data can be removed by uninstalling the application and deleting the application's local settings and log folders.

## Summary

SRT USB CAM is designed to keep settings and logs local. Camera video is sent only to the SRT destination configured by the user.

---

**SRT USB CAM Team**
May 9, 2026
