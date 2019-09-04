# Telegraf Client

A C# client to interface with InfluxDb Telegraph client, forked from the 
awesome [StatsD client](https://github.com/Pereingo/statsd-csharp-client) by Goncalo Pereira.

Install the client via NuGet with the [Telegraf package](http://nuget.org/packages/Telegraf).

## Usage

At app startup, configure the `Metrics` class (other options are documented on `MetricsConfig`):

``` C#
Metrics.Configure(new MetricsConfig
{
  StatsdServerName = "hostname",
  Tags = new[]{"app=prod"}
});
```

Then start measuring all the things!

``` C#
Metrics.Counter("stat-name");
Metrics.Time(() => myMethod(), "stat-name"));
Metrics.GaugeAbsolute("gauge-name", 35);
Metrics.GaugeDelta("gauge-name", -5);
Metrics.Set("something-special", "3");
```

You can also time with the disposable overload:

## Development
* Please have a chat about any big features before submitting PR's
* NuGet is packaged as an artefact. Grab that `*.nupkg` and upload it to NuGet.org
