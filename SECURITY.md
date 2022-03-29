# Security Policy

## Supported Versions

Use this section to tell people about which versions of your project are
currently being supported with security updates.

| Version | Supported          |
| ------- | ------------------ |
| 5.1.x   | :white_check_mark: |
| 5.0.x   | :x:                |
| 4.0.x   | :white_check_mark: |
| < 4.0   | :x:                |

## Reporting a Vulnerability

Use this section to tell people how to report a vulnerability.

Tell them where to go, how often they can expect to get an update on a
reported vulnerability, what to expect if the vulnerability is accepted or
declined, etc.
#define LOCAL // Comment if your target is remote

using Vortex.Adapters.Connector.Tc3.Adapter;

namespace HansPlc
{
    public static class Entry
    {
#if LOCAL
        const string AmsId = null; // your ams id or set to 'null' if local
        const int Port = 851;
#else
        const string AmsId = "172.20.10.2.1.1"; // set your target ams id
        const int Port = 851;
#endif
        public static HansPlcTwinController HansPlc { get; } = new HansPlcTwinController(Tc3ConnectorAdapter.Create(AmsId, Port, true));
    }
}
