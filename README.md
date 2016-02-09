# Multi-tenant LoopBack POC

This is a POC on implementing multi-tenancy in LoopBack using isolated processes and data sources.

## Features

* Customize `model-config.json` and `datasources.json` for each tenant
* Each tenant can have custom middleware, components, and boot scripts, if required

## Gateway Manager

The gateway manager works as the front facing proxy for the tenany apps. It is available as the `mtg` command on the command line.

The gateway must be started before the tenant apps can be accessed.

**Start gateway**

```
$ mtg start
```

**Restart gateway**

```
$ mtm restart
```

**Stop gateway**

```
$ mtm stop
```

## Tenant Manager

The tenant manager is used for managing tenants and their models. It is available as the `mtm` command on the command line.

Use a `tenant id` composed of alphanumerical characters only.

The tenant config files must be manually configured in the POC.

**Add tenant**

```
$ mtm add <tenant id>
```

**Remove tenant**

```
$ mtm remove <tenant id>
```

**Start tenant app**

```
$ mtm start <tenant id>
```

**Stop tenant app**

```
$ mtm stop <tenant id>
```

**Restart tenant app (after making configuration changes)**

```
$ mtm restart <tenant id>
```

**Create model for tenant**

```
$ mtm model <tenant id:model name>
```
