---
hide:
  - footer
---

# Neeno SDK

Welcome to the Neeno SDK! It is designed to help you interact with your Neeno
devices.

It is a cross-platform solution (Windows, macOS, and Linux) designed to help
you accelerate your development through:

- **Data Acquisition**: Access to the raw data from the sensors.
- **Data Logging**: Store data in a file for later analysis.
- **Framework Integration**: Interfaces to major Frameworks and Libraries.

Advanced users can also:

- Access raw data from the sensors.
- Create their own applications using the SDK.
- Compile the SDK from source.
- Customize the firmware of the device.

We highly recommend that you join our [Github Community](https://github.com/MyNeeno)
to share your ideas, get help from other developers, and be the first to know
about the newest features and updates.

## Reporting Issues

Security issues and bugs should be reported privately, via email, to the Neeno
Team at <contact@myneeno.com>.

You should receive a response within 24 hours. If for some reason you do not,
please follow up via email to ensure we received your original message.

## Fire it up!

Once you power up your armband it will immediately look for a connection with
your central device using BLE.

In the [next page](Software/introduction.md) we show you how to get our Python SDK.

If you have the provided credentials a very basic implementation looks like
this:

```python
import neeno
neeno.connect("credentials.json")
```

Done! You are now connected to your Neeno device via BLE, and can start
interacting with it in Python, and use the streamed data as you please.

How come? Well, in the following pages you will find out.

Ready to start? Take your [first steps](Software/introduction.md).

---

<p style="text-align: center;">Go to <a href="https://myneeno.com">myneeno.com</a></p>
