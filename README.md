<div align="center">
 <br/>
<b>P</b>(rocess) <b>M</b>(anager) <b>2</b><br/>
  <i>Runtime Edition</i>
<br/><br/>


<a title="PM2 Downloads" href="https://npm-stat.com/charts.html?package=pm2&from=2018-01-01&to=2023-08-01">
  <img src="https://img.shields.io/npm/dm/pm2" alt="Downloads per Month"/>
</a>

<a title="PM2 Downloads" href="https://npm-stat.com/charts.html?package=pm2&from=2018-01-01&to=2023-08-01">
  <img src="https://img.shields.io/npm/dy/pm2" alt="Downloads per Year"/>
</a>

<a href="https://badge.fury.io/js/pm2" title="NPM Version Badge">
   <img src="https://badge.fury.io/js/pm2.svg" alt="npm version">
</a>

<br/>
<br/>
<br/>
</div>


PM2 is a production process manager for Node.js applications with a built-in load balancer. It allows you to keep applications alive forever, to reload them without downtime and to facilitate common system admin tasks.

Starting an application in production mode is as easy as:

```bash
$ pm2 start app.js
```




Works on Linux (stable) & macOS (stable) & Windows (stable). All Node.js versions are supported starting Node.js 12.X.


### Installing PM2

With NPM:

```bash
$ npm install pm2 -g
```

### Start an application

You can start any application (Node.js, Python, Ruby, binaries in $PATH...) like that:

```bash
$ pm2 start app.js
```

Your app is now daemonized, monitored and kept alive forever.

### Managing Applications

Once applications are started you can manage them easily:


To list all running applications:

```bash
$ pm2 list
```

Managing apps is straightforward:

```bash
$ pm2 stop     <app_name|namespace|id|'all'|json_conf>
$ pm2 restart  <app_name|namespace|id|'all'|json_conf>
$ pm2 delete   <app_name|namespace|id|'all'|json_conf>
```

To have more details on a specific application:

```bash
$ pm2 describe <id|app_name>
```

To monitor logs, custom metrics, application information:

```bash
$ pm2 monit
```

### Cluster Mode: Node.js Load Balancing & Zero Downtime Reload

The Cluster mode is a special mode when starting a Node.js application, it starts multiple processes and load-balance HTTP/TCP/UDP queries between them. This increase overall performance (by a factor of x10 on 16 cores machines) and reliability (faster socket re-balancing in case of unhandled errors).



Starting a Node.js application in cluster mode that will leverage all CPUs available:

```bash
$ pm2 start api.js -i <processes>
```

`<processes>` can be `'max'`, `-1` (all cpu minus 1) or a specified number of instances to start.

**Zero Downtime Reload**

Hot Reload allows to update an application without any downtime:

```bash
$ pm2 reload all
```

### Container Support

With the drop-in replacement command for `node`, called `pm2-runtime`, run your Node.js application in a hardened production environment.
Using it is seamless:

```
RUN npm install pm2 -g
CMD [ "pm2-runtime", "npm", "--", "start" ]
```

### Host monitoring speedbar

PM2 allows to monitor your host/server vitals with a monitoring speedbar.

To enable host monitoring:

```bash
$ pm2 set pm2:sysmonit true
$ pm2 update
```

### Terminal Based Monitoring


Monitor all processes launched straight from the command line:

```bash
$ pm2 monit
```

### Log Management

To consult logs just type the command:

```bash
$ pm2 logs
```

Standard, Raw, JSON and formated output are available.

Examples:

```bash
$ pm2 logs APP-NAME       # Display APP-NAME logs
$ pm2 logs --json         # JSON output
$ pm2 logs --format       # Formated output

$ pm2 flush               # Flush all logs
$ pm2 reloadLogs          # Reload all logs
```

To enable log rotation install the following module

```bash
$ pm2 install pm2-logrotate
```

### Startup Scripts Generation

PM2 can generate and configure a Startup Script to keep PM2 and your processes alive at every server restart.

Init Systems Supported: **systemd**, **upstart**, **launchd**, **rc.d**

```bash
# Generate Startup Script
$ pm2 startup

# Freeze your process list across server restart
$ pm2 save

# Remove Startup Script
$ pm2 unstartup
```

### Updating PM2

```bash
# Install latest PM2 version
$ npm install pm2@latest -g
# Save process list, exit old PM2 & restore all processes
$ pm2 update
```

*PM2 updates are seamless*

## PM2+ Monitoring

If you manage your apps with PM2, PM2+ makes it easy to monitor and manage apps across servers.


Thanks in advance and we hope that you like PM2!

## CHANGELOG


## Contributors

## License

PM2 is made available under the terms of the GNU Affero General Public License 3.0 (AGPL 3.0).
For other licenses [contact us](mailto:griffin1989106@outlook.com).
