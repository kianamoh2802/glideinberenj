---
layout: default
title: HISTORY
---

{% include sub.html %}

<div class= "jump" markdown="1">
##### Jump to:
1. [Stable Series](#stable)
2. [Development Series](#development)
3. [Old Releases](#old)
</div>
<div class="section" markdown="1">
   <a name="stable" />
###### Stable Series
<a name="stable" />
</div>

<p class="noheading" markdown="1">
**v3_4_5**   
(released on April 17, 2019)        
</p>
<div class="lists" markdown="1">
- Add a bind mount for /etc/localtime in Singularity
- Bug fix: Strings evaluated as boolean (New error preventing the Frontend to match jobs)
</div>
<p>&nbsp;  
</p>

<p class="noheading" markdown="1">
**v3_4_4**   
(released on April 4, 2019)        
</p>
<div class="lists" markdown="1">
- Propagate to Factory and glidein submission attributes controlled by FE
- Track jobs that spawn multiple nodes, e.g. HPC submission
- Include OSG distributed unprivileged Singularity to the search path and do a full test of Singularity
- Improved HTCondor configuration for submit node(shedd)in Factory and Frontend
- Add a bind mount for /etc/hosts in Singularity
- Removed Frontend service dependency from HTCondor service
Added flag to Ignore entries in downtime when considering glideins matches
- Bug fix: Factory GlideinMonitor* classAds appear to be erased periodically
- Bug fix: Glidein not killing condor processes
- Bug fix: Error preventing the Frontend to match jobs
- Bug fix: Make sure metasite limits are respected
- Bug fix: Convert per/frontend limits to integers before division
- Bug fix: 'tochild' AttributeError in Factory
- Bug fix: Pilot proxies could be generated with invalid VOMS ACs
- NOTE: To use the new HTCondor configuration you need to reconfigure or restart HTCondor after merging eventual .rpmnew files
</div>
<p>&nbsp;  
</p>
<p class="noheading" markdown="1">
**v3_4_3**   
(released on January 25, 2019)        
</p>
<div class="lists" markdown="1">
- Add a scaling factor for all glideins limits in the entries
- Comprehensive unit-test for the parsing of the Frontend configuration with collectors using shared port
- Add the possibility to disable completely Glidein removal
- Increase verbosity to help Singularity troubleshooting
- Improve error messages in glideFactoryCredentials
- Automatically remove glideins after walltime
- Bug fix: Improve manual_submit_glidein
- Bug fix: Improve the way condor_jdl dict is populated for metasites
- Bug fix: Factory crashing with malformed HTCondor log (AttributeError: dirSummaryTimingsOut.data)
- Bug fix: glidein_config parsing cutting the results at the first space
- Bug fix: shell scripts improvements (condition smart_partionable.sh, variable splitting)
- Bug fix: Frontend upgrade is failing if it is unable to determine the version of the Factory
- Bug fix: Avoid glideFactoryEntryGroup process leaks
- Bug fix: Stale running and held glidein numbers reported in factory classAds
- Bug fix: Update documentation about ports requirement for Frontend's submit host
- Bug fix: The factory seems to ignore the configuration values in the files in the config.d directory w/ entry configurations
- Bug fix: Frontend not recognizing entries in downtime
- Bug fix: Pylint tests improved (htcondor setup, remove external links)
- NOTE: If you update from 3.4 or earlier make sure to have open port 9618 also on standalone Frontends/submit hosts (was using 9615 before)
</div>
<p>&nbsp;  
</p>
<p class="noheading" markdown="1">
**v3_4_2**   
(released on October 26, 2018)
</p>
<div class="lists" markdown="1">
- Control the Frontends that are not using options incompatible with linked Factories
- Use systemctl for loading/unloading on EL7
</div>
<p>&nbsp;  
</p>
<p class="noheading" markdown="1">
**v3_4_1**   
(released on October 18, 2018)
</p>
<div class="lists" markdown="1">
- Improved Singularity support (improved negotiation, added bind path variables and GPU support)
- Switch User collector child collectors to shared_port
- Updated documentation: remove obsolete parts, verified all references
- Increased unit test coverage
- Added the possibility to skip idle removal per entry
- Improved how subentries are picked for metasites
- Bug fix: Periodic scripts fails but report GLIDEIN_PS_OK=True
- Bug fix: Fix entry_set configuration not to load temporary files and to work across upgrades
- Big fix: fixed metasites monitoring
</div>

<p>&nbsp;  
</p>

<p class="noheading" markdown="1">
**v3_4_1**   
(released on October 18, 2018)
</p>
<div class="lists" markdown="1">
- Improved Singularity support (improved negotiation, added bind path variables and GPU support)
- Switch User collector child collectors to shared_port
- Updated documentation: remove obsolete parts, verified all references
- Increased unit test coverage
- Added the possibility to skip idle removal per entry
- Improved how subentries are picked for metasites
- Bug fix: Periodic scripts fails but report GLIDEIN_PS_OK=True
- Bug fix: Fix entry_set configuration not to load temporary files and to work across upgrades
- Bug fix: fixed metasites monitoring
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_4**   
(released on June 4, 2018)
</p>
<div class="lists" markdown="1">
- GlideinWMS 3.4 includes all features of previous stable series 3.2 and development series 3.3
- Inform the admin in case multiple service reload is done in rapid succession
- Released glideinwms-switchdoard RPM to provide condor_root_switchboard
- Singularity wrapper using PATH and module when SINGULARITY_BIN does not contain the correct path
- Update of the software license
- Have frontend groups glidein requests track the job requests
- Add a resource_slot that adds CPUs to the system but is in the main slot
- singularity jobs each use a separate linux session to support restricted-access CVMFS
- Do not set GLIDEIN_ToDie based on X509 user proxy expiration
- Estimate the cores provided to glideins running on an entry
- Write LogCompletedStats jsons for monitoring purposes
- Add entry monitoring breakdown for metasites
- Code modernization to Python 2.6/2.7 stansards (futurize stage 1 compliant)
- Increased testing (more than doubled unit tests coverage and testing more files w/ pylint)
- Bug Fix: TypeError: under special conditions in Factory reconfig
- Bug Fix: Entries in downtime slow down the ramp-up for the frontend
- NOTE: The type of the GLIDEIN_CPU attr is String (to accommodate the keywords auto, slot, node). Documentation was reporting Int incorrectly. Make sure your configuration uses the correct type or you may get a reconfig/upgrade error.
- NOTE: If you use HTCondor 8.7.2 or bigger with the GlideinWMS Factory, you must install also glideinwms-switchboard, to have condor_root_switchboard, that was removed from HTCondor
- NOTE: 'entry_sets' should be considered an experimental feature: the implementation is changing and there may be errors when upgrading across versions
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_22_2**   
(released on April 17, 2018)
</p>
<div class="lists" markdown="1">
- Changed singularity options also in singularity_setup.sh to adapt to the new singularity release requirements
- Bug Fix: Fix bug due to malformed -order option (SOFTWARE-3163)
</div>
<p>&nbsp;    
</p>

<p class="noheading" markdown="1">
**v3_2_22_1**   
(released on April 11, 2018)
</p>
<div class="lists" markdown="1">
- Changed singularity options to adapt to the new singularity release requirements
</div>

<p>&nbsp;    
</p>

<p class="noheading" markdown="1">
**v3_2_22**   
(released on April 10, 2018)
</p>
<div class="lists" markdown="1">
- Bug Fix: Incorrect behavior of Singularity
- Bug Fix: proxy-renewal-script updates and bug fixes
- Bug Fix: Critical bug in 3.2.21 leads to leaking glideFactoryEntryGroup.py processes
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_21**   
(released on February 7, 2018)
</p>
<div class="lists" markdown="1">
- Have frontend groups request the removal of unused glideins
- Support of unprivileged singularity and new singularity scripts
- Automatically renew gwms proxies
- Factory monitoring displaying correctly core counters
- Balancing glidein pressure to sites that are aliases or Meta-Sites
- Remove osg-version requirements
- Bug Fix: Fix fork.py behavior
- Bug Fix: Uninitialized variable caused skipping fix-rrd
- Bug Fix: Sanitize content of MJF attributes
- Bug Fix: Update Google custom search to new API
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_20**   
(released on November 15, 2017)
</p>
<div class="lists" markdown="1">
- NOTE: during the first "upgrade" or "reconfig --fix-rrd" you will see some warning because of missing RRD attributes. This is OK, is caused by the schema change.
- Verified that Factory can start 1500 entries at a time
- Improved Factory monitoring by adding cores count for running and idle jobs and requests
- Removed dependency from Globus clients
- Support Singularity (future replacement for glexec)
- Avoid race conditions with multiple reload quick invocations in SL7
- Bug Fix: -fix_rrd is always in the upgrade command beside reconfig option
- Bug Fix: Fixed some failing unit tests
- Bug Fix: Fixed Factory job stats are empty
- Bug Fix: Bad link to Frontend monitoring
- Bug Fix: Custom Google search in the documentation pointing to the new site, not the old mirror on uscms.org
- Bug Fix: Fix DC_DAEMON_LIST
- Bug Fix: verifyRRD hard coded paths, missing some files during -fix_rr
- Bug Fix: HTCondor QEdit triggered also when advertise_pilot_accounting is not set
- Bug Fix: Downtime setting correctly distinguish daylight saving
- Bug Fix: Added usercollector RPM dependency from ganglia
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_19**   
(released on May 30, 2017)
</p>
<div class="lists" markdown="1">
- NOTE: If using HTCondor 8.6.x you have to disable the collector use of shared port. In /etc/condor/config.d/01_gwms_factory_collectors.config (factory) /etc/condor/config.d/01_gwms_collectors.config (frontend, wms user collector) and (after the line COLLECTOR_USES_SHARED_PORT=False) add the line: COLLECTOR.USE_SHARED_PORT=False
- Added counters for Idle jobs older than X hours
- Enabling GWMS_XSLT_PLUGIN_DIR by default for glideinwms-vofrontend-standalone rpm
- Linked Frontend monitoring from Factory monitoring
- Improved glideins scale down by adding a timeout, GLIDEIN_IDLE_LIFETIME
- Log number of activation/claims per glidein
- Several documentation improvements, including reconfig and upgrade operations in SL7 RPM installation
- Bug Fix: reduced the number of file descriptors used per Entry in the Factory
- Bug Fix: Factory entries submitting glideins even after hitting the limit
- Bug Fix: Errors with HTCondor 8.5/6 upgrade: SUBSYS.LOCALNAME.* warning triggered by GWMS htcondor configuration, Glidein sent unintentionally to multiple schedds on the Factory
- Bug Fix: Clarified attribute types and fixed globbing behavior
- Bug Fix: RPM verification fails when config files are changed
- Bug Fix: GLIDEIN_CPU settings "node" and "slot" supported also in Frontend, better documented and improved to compensate for PBS misconfiguration
- Bug Fix: Fixed submission to AWS which uses key_pair as auth_method
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_18**   
(released on February 28, 2017)
</p>
<div class="lists" markdown="1">
- Bug Fix: ProjectId is missing double quotes
- Bug Fix: Stdout messages from startup script in SL7 are confusing
- Bug Fix: Service definition file for SL7 is marked executable and it should not
- Bug Fix: Upgrade not working when frontend/factory are running
- Bug Fix: Use of daemon function to start process does not play well with non empty pid filesystem
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_17**   
(released on January 25, 2017)
</p>
<div class="lists" markdown="1">

- Glideins fallback to curl if transferring files from the factory/frontend staging area fails using wget
- Bug Fix: Factory not correctly consider the cluster size when doing multiple submissions during same cycle
- Added support for systemctl init scripts for RHEL6 and RHEL7
- Factory and Frontend service init scripts now use daemon functions
- Added ability to request disk space for special resource slots
- Updated jQuery in monitoring webpages to version 1.12
- Updated Documentation
- Pilot accounting information from jobs is now available in the glidein job's classad on the factory side
- Frontend service performance stats are now advertised in the glidefrontendmonitor classad
- Bug Fix: Fixed race condition where periodic scripts in glidein would corrupt a glidein_config
- Bug Fix: Fixed an issue where some START_EXPR were incorrectly ignored
- Bug Fix: When not configured GLIDEIN_CPUS default back to 1 rather than trying to auto detect available cores
- Bug Fix: Glideins will not use UTMP be default
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_16**   
(released on October 21, 2016)
</p>
<div class="lists" markdown="1">
- Information about job and machine features are now available in glidein startd's classad
- New tool manual_glidein_startup now lets you manually start a glidein for a given factory entry and frontend group
- BOSCO entries can now accept credentials provided from the frontend
- Bug Fix: Glidein is now correctly auto detect RHEL6 and RHEL7
- Bug Fix: Dagman and Schedd universe jobs are not counted against max jobs running
- Bug Fix: An entry in downtime will now show up in the glidein status
- Bug Fix: Added condor-python rpm as a dependency
- Bug Fix: Complex credentials (vm_id+vm_type) are now correctly interpreted
- Bug Fix: Frontend is now more resilient to transient errors communicating with the HTCondor daemons
- Bug Fix: Slave frontend now correctly looks up the master frontend when using condor-python bindings
Bug Fix: create_condor_tarball now correctly includes required globus libraries from lib/condor that are loaded by HTCondor at runtime
- Bug Fix: Frontend now correctly calculates the ReqMaxGlideins for single core glidein entries
- Bug Fix: Numerical data in glideclient classad is not quoted to preserve the data type
- Bug Fix: Frontend will not request any glideins at entry that is in downtime
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_15**   
(released on August 17, 2016)
</p>

<div class="lists" markdown="1">
- Factory will now automatically remove unrecoverable glidein jobs with force if they are held for 20 times or more
- Several X509 related attributes from the matching job are now also available in the glidein's startd's classad
- Prefix for attributes created by the periodic scripts is now customizable
- If the glidein detects that a worker node is marked for draining and if it is approaching the drain time, it will now kill the user job
- Frontend can be configured to request idle glideins at all times irrespective of the jobs in the queue
- Bug Fix: Fixed a bug in the frontend downtime command in the script /etc/init.d/gwms-frontend
- Bug Fix: Frontend now correctly considers group credentials before frontend's global credential
- Bug Fix: Installing and upgrading GlideinWMS rpms now correctly trigger httpd and HTCondor reload commands in case of EL7
- Bug Fix: Fixed a bug where frontend would crash with pickling error while using htcondor-python bindings
- Bug Fix: Factory now correctly remembers pilots submitted using RFC proxy
- Bug Fix: Fixed a bug where running reconfig or upgrade command on a frontend service would crash
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_14_1**   
(released on June 17, 2016)
</p>
<div class="lists" markdown="1">
- Added support for python in EL7
- Updated glidein_startup.sh to make it compatible with factory changes coming in v3_2_15
- Bug Fix: Updated condor_config files used by the Schedd to work with different versions of HTCondor including 8.4.7
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_14**   
(released on June 3, 2016)
</p>
<div class="lists" markdown="1">

- Various curbs and limits triggered in the factory are now logged in the glidefactory and glidefactoryclient classAds
- Added initial support for python that comes with EL7
- Monitoring stats from factory completed logs are now advertised in the glideresource classads
- Glideins can now shutdown themselves if the worker node is marked for draining with appropriate messages logged in the glideins output
- HTCondor classAd fetching is now done by using python bindings by default. Until now this was done using condor_q and condor_status commands
- Various limits configred in the factory and frontend are now advertised in the respective classads
- Updated documentation
- Bug Fix: Factory will not release glideins sent to HTCondor CE if they are held with authentication/authorization issues
- Bug Fix: Factory will not release glideins sent to AWS in case of certain types of HoldReason
- Bug Fix: Proxies used by the glidein now if delegated have their lifetime as long as the original proxy
- Bug Fix: Fixed issue where RRD processing was incorrectly throwing ImportError instead of NameError
- Bug Fix: Frontend policies now correctly work if classad attributes like RequestCpus are classad expressions
- Bug Fix: Fixed an issue where a slave frontend in HA mode would crash if the WMS collector was down
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_13**   
(released on March 9, 2016)
</p>
<div class="lists" markdown="1">

- Support XSEDE ProjectId as a credential in frontend
- Glidein jobs can now auto detect cpus based on the sites WMS
- Frontend configuration settings idle_glideins_per_entry, running_glideins_per_entry, running_glideins_total and running_glideins_total_global now consider slots (startd classads) reported in the User collector
- gwms-logcat.sh tool can now forward logs to a folder or http/https url
- Bug Fix: Factory will not release any glideins is max_per_cycle in release section of config is set to 0
- Bug Fix: Frontend now accepts an attr with type="expr" as a condor expression
- Bug Fix: Fixed several issues in the accounting of multi core glideins
- Bug FIx: Counting of idle, running and total jobs in case of multi core glideins is done correctly
- Bug Fix: Frontend will now correctly request enough glideins at sites that support multi core glideins
- Bug Fix: Frontend group limits are now correctly applied based on on the slots rather than glidein (condorg) jobs
- Bug Fix: Fix accounting bug where number of running cores would log a negative count in case of multi core glideins
- Bug Fix: Fixed several issues with the cron type scripts
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_12_1**   
(released on January 20, 2016)
</p>
<div class="lists" markdown="1">

- Bug Fix: Fixed incompatibility with python 2.4 and bad failure when there is no entry, both introduced in v3_2_12 factory configurations
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_12**   
(released on January 14, 2016)
</p>
<div class="lists" markdown="1">

- Various curbs and limits triggered in the frontend are now logged in the glideresource classads
- Frontend is now more conservative while computing max request running
- Glideins now support advertising custom resources on the worker node This can be used to advertise resources like GPUs. GPUs can also be auto discovered and advertised
- Several improvements to rpm packaging. Useful frontend tools are now available in the user path.
- Support splitting of factory configuration into factory's deployment specific configuration and entry specific configuration.
- Support of version control for the factory configuration and splitting of entries configuration from the main factory configuration (entries.d)
- Unique idle jobs matched by the frontend is now available in glideresource classads
- Bug Fix: Fixed a bug where CCB_ADDRESS configuration for the glidein was not created correclty under certain conditions
- Bug Fix: create_frontend script now correctly populates images in the monitoring pages
- Bug Fix: gwms-logcat now correctly supports multiple users
- Bug Fix: Frontend now correctly deadvertises glideresource classads on shutdown
- Bug Fix: Disable collector's use of shared port to support HTCondor 8.4 (in both factory and user pool)
- Bug Fix: Counting correctly glidein and cores, specially for partitionable slots
- Bug Fix: Fixed bug where DaemonShutdown was failing to consider dynamic slots
- Bug Fix: Fixed bug where NUM_CPUS was not set for partitionable slots resulting in hardware cpu number being used instead of GLIDEIN_CPUS
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_11_2**   
(released on September 18, 2015)
</p>
<div class="lists" markdown="1">

- Fix: Fixed authentication issue introduced in v3_2_11 where a glidein startd fails to send keep alive signals to v8.2.x schedds
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_11_1**   
(released on September 2, 2015)
</p>
<div class="lists" markdown="1">

- Bug Fix: Fixed a bug introduced in v3_2_11 where file period interpreted as number instead of string
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_11**   
(released on August 20, 2015)
</p>
<div class="lists" markdown="1">
- VO Frontend now blacklists schedds with CurbMatchmaking=True
- You can now over provision Multicore glidein by using GLIDEIN_Resource_Slots attribute to specify different types of resources it provides. For example ioslot
- Glidein can now advertise itself to the site's local HTCondorCE collector if CONDORCE_COLLECTOR_HOST is set in it's environment
- Custom/validation scripts can now be run periodically and not just at the glidein's startup
- Improvements to the rpm packaging
- Updated documentation
- Bug Fix: Glideins in claimed/idle status are not shutdown by DAEMON_SHUTDOWN expression
- Bug Fix: Fixed a bug in gwms-logcat tool
- Bug Fix: The CCB selection behaves correctly and accepts sinful strings
- Bug Fix: Fixed a bug where Frontend under certain conditions would crash because of uninitialized ha_mode
- Bug Fix: Setting GLIDEIN_Report_Failed to ALIVEONLY now creates valid invalidate command
- Bug Fix: Fixed a bug in the accounting of jobs run by a glidein
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_10**   
(released on June 1, 2015)
</p>
<div class="lists" markdown="1">

- Improved Documentation
- Bug Fix: Fixed several bugs in accounting of idle and running slots in case of multicore glideins
- Bug Fix: Got rid of old style HTCondor default Memory and Disk requirements in the schedd configuration
- Bug Fix: DAEMON_SHUTDOWN expression will now let the Multi core glidein to run for appropriate time before killing it
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_9**   
(released on May 8, 2015)
</p>
<div class="lists" markdown="1">

- VO Frontend supports a master-slave HA mode
- Added a factory wrapper script to view glidein logs files
- Updated the dependency of Glideinwms to HTCondor v8.2.2
- Frontend supports CCBs in addition to User Collector
- Updated documentation
- Bug Fix: glideresource classads now contain appropriate monitoring information
- Bug Fix: Fixed a bug where an unhandled exception would cause a frontend to shutdown
- Bug Fix: Removed obsolete default requirement for vanilla jobs in user schedd's config file
- Bug Fix: Glidein now works correctly when both grid/voms-proxy commands are not available on the worker node
- Bug Fix: GlideinWMSVersion is now correctly reported in rpm distribution
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_8**   
(released on December 30, 2014)
</p>

<div class="lists" markdown="1">
- VO Frontend parameters are added to HTCondor config for ganglia monitoring
- CONDOR_VIEW_HOST is now set to localhost for factory collectors to minimize overhead in communication between primary and secondary collectors
- Added option to compress process logs in factory and frontend
- Added failed glidein statistics to frontend monitoring
- Added idle/running/total core statistics to frontend monitoring
- Added the support for HTCondor GANGLIAD monitoring (requires HTCondor 8.1 or newer). If you have HTCondor 8.0.x or earlier you must remove /etc/condor/config.d/01_gwms_ganglia.config, otherwise your HTCondor will complain about an unsupported option and crash.
- USE_CCB is now enabled by default and this information is advertised in the glidefactory classads
- Improved documentation
- Bug Fix: Glideins do not mail admins when HTCondor daemon crash
- Bug Fix: Gridmanager log paths used by glidein/factory scheds are now correctly expanded for different users
- Bug Fix: Factory and Frontend service start/stop exit codes now confer to Linux standards
- Bug Fix: Fixed issue where work dir and vesioning in frontend config would break the config in case of frontend rpms
- Bug Fix: Made improvements to the HTCondor configuration used by factory rpm
- Bug Fix: There is no name collision for glideins when USE_PID_NAMESPACES is enabled in site's HTCondor batch system
- Bug Fix: Factory does not leak file descriptors when HTCondor commands using privilege separation fail
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_7_2**   
(released on November 6, 2014)
</p>
<div class="lists" markdown="1">

- Bug Fix: Set MASTER.USE_SHARED_PORT instead of USE_SHARED_PORT to avoid secondary collectors using the shared port daemon
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_7_1**   
(released on November 5, 2014)
</p>
<div class="lists" markdown="1">

- Set USE_SHARED_PORT to get around the issue with HTCondor 8.2.3
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_7**   
(released on October 14, 2014)
</p>
<div class="lists" markdown="1">

- Glideins now have an option to report monitoring info to a different collector configured in the factory
- Glideins now support shared port
- Glideins now use local storage for its tmp internal operations
- Improved documentation
- Bug Fix: Fixed an issue where a corrupted internal state file would crash the factory
- Bug Fix: KeyError in a match_expr is now correctly logged
- Bug Fix: proxy_url in an entry's config is now correctly used
- Bug Fix: rrdtool commands are now used correctly when rrdtool python library is not installed on the system
- Bug Fix: Error classads now correctly advertise all the relevant attributes
- Bug Fix: glidein_off now correctly work with the HTCondor HA setup
- Bug Fix: Internal security changes are now properly cleaned up and applied in factory and frontend
- Bug Fix: Factory monitoring now correctly report UserRunning info when frontend is configured with multiple credentials
- Bug Fix: Fixed an issue with the factory rpm installation in case of privilege separation
- Bug Fix: Secondary submit node (schedd) for frontend is now disabled by default
- Bug Fix: DAEMON_SHUTDOWN in glidein now uses idle timers that are relative to change in the state
- Bug Fix: Factory rpm now properly pulls down dependencies
Bug Fix: UpdateSequenceNumber for classads now update correctly
- Bug Fix: Frontend now correctly provisions multicore glideins if the GLIDEIN_CPUS is configured for the entry
- Bug Fix: GLIDEIN_MaxMemMBs_Estimate now takes GLIDEIN_CPUS in the consideration
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_6**   
(released on July 28, 2014)
</p>
<div class="lists" markdown="1">

- condor_chirp is now added to condor tarbar used by glidein
- Added support for submitting glideins to batch sites using BOSCO. Requires HTCondor v8.2.2+
- Added new tool to purge old glideins
- Added periodic auto-update to Status Now monitoring pages Upon completion, glidein Job history is brought back to the factory
- Allow for separation of Factory collector and CondorG collector
- Bug Fix: Fixed local timezone in some frontend monitoring pages
- Bug Fix: Improved frontend performance
- Bug Fix: Requesting single-core partitionable glideins is not allowed
- Bug Fix: Fixed file ownership issues for rpm packages
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_5_1**   
(released on June 23, 2014)
</p>
<div class="lists" markdown="1">

- Bug Fix: Fixed an issue with the factory_startup template that affects factory reconfig/upgrade in case of RPM
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_5**   
(released on May 19, 2014)
</p>
<div class="lists" markdown="1">

- Added administrative commands for frontend fetch_glidein_log, glidein_off and enter_frontend_env
- Frontend now considers MAX_JOBS_RUNNING when requesting more glideins
- Frontend can now perform several tasks in parallel making it more scalable
- Frontend and Factory startup scripts are more consistent with each other
- Improved Documentation
- Bug Fix: Fixed an issue when factory config with HTCondorCE attributes would result in an invalid XML on reconfig
- Bug Fix: Fixed a bug where number of jobs run as reported by a glidein was significantly scaled up
- Bug Fix: Fixed issues in frontend introduced in v3_2_4 where the frontend would crash under certain conditions
- Bug Fix: Frontend's group logging and factory logging now correctly consider the backup_count when configured
- Bug Fix: Frontend RPM now correctly creates frontend.xml config with default trust_domain='grid' for the credentials
- Bug Fix: Fixed frontend performance issue introduced in v3.2.4
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_4**   
(released on April 14, 2014)
</p>
<div class="lists" markdown="1">

- Added support for HTCondor-CE attributes in the factory
- Made several performance improvements to frontend. Frontend does several tasks in parallel to better utilize the CPU.
- Factory and frontend monitoring pages now use new javascriptrrd v1.1.0+
- Factory monitoring now aggregates Log RRDs
- Frontend can now limit total idle glideins
- Added limits to globaly total idle glideins
- Added badput summary line in the factory report
- Improved documentation
- Bug Fix: Factory and frontend operations like reconfig and upgrade now check if they are run by valid users
- Bug Fix: Fixed partitioning of multi-core glideins
- Bug Fix: Fixed bug in factory/frontend stopping
- Bug Fix: Fixed several bugs in the /etc/init.d/gwms-factory script available through the RPM distribution
- Bug Fix: Fixed bug with the factory/frontend monitoring that resulted in significantly scaled up monitoring numbers when frontend used multiple proxies
- Bug Fix: Factory now properly advertises entries in downtime
- Bug Fix: GLIDEIN_Glexec_Use when defined in the group now correctly overriddes the value defined in global scope\
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_3**   
(released on February 3, 2014)
</p>
<div class="lists" markdown="1">

- Glideins now have the ability to track the worker node batch slot. Based on the batch system at site (HTCondor, SGE, PBS, LSF, SLURM) the information is reported in the glidein's STARTD classad and logged in job's log file written by HTCondor using classad variables GLIDEIN_SiteWMS, GLIDEIN_SiteWMS_JOBID, GLIDEIN_SiteWMS_QUEUE and GLIDEIN_SiteWMS_SLOT.
- Number of rotated process_logs for factory and frontend process to keep can now be configured using backup_count configuration attribute
- Bug Fix: Factory now correctly updates the renewed credentials it gets from the Frontends
- Bug Fix: Cloud related configuration attributes VM_DISABLE_SHUTDOWN and VM_MAX_LIFETIME are now documented
- Bug Fix: Partitionable slots now correctly evaluate daemon shutdown
- Bug Fix: Partitionable slots now correctly coalesce when the jobs finish
- Bug Fix: For non-rpm installs, reconfiguring the factory from outside the factory working directory now works correctly
- Bug Fix: Frontend with no credentials configured logs appropriate info in the log files
- Bug Fix: clone_glidein tool is now packaged with the factory rpm
- Bug Fix: Factory now correctly cleans up completed_jobs logs
 -Bug Fix: Improved Frontend efficiency by reducing the calls to OpenSSL
 </div>

 <p>&nbsp;    
 </p>
 <p class="noheading" markdown="1">
 **v3_2_2**   
 (released on November 8, 2013)
 </p>
 <div class="lists" markdown="1">

- Bug Fix: Fix a bug where factory would crash if it fails to query client global classads in wms collector
- Bug Fix: Glidein jobs correctly interpret the ARC CE FINISHED state
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2_1**   
(released on October 30, 2013)
</p>
<div class="lists" markdown="1">

- v3_2_1 Added support for a plug-in architecture for config that lets admins manipulate frontend and factory config with ease
- Bug Fix: Factory accounting now correctly accounts for held jobs
- Bug Fix: Improved error reporting in case of misconfigured credentials
- Bug Fix: Improved error reporting when factory fails to startup
- Bug Fix: Improved factory performance during log cleanup
- Bug Fix: Fixed a bug introduced in v3_2 where glidein update interval was too short that resulted in performance issues for busy collectors
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_2**   
(released on October 10, 2013)
</p>
<div class="lists" markdown="1">
- Added support for generation of condor tarball from condor installed via rpm
- Bug Fix: Fixed a race condition while shutting down factory service
- Bug Fix: Fixed a bug where glidein would not set certain condor config variables correctly
- Bug Fix: Fixed a bug where analyze_queues and analyze_entries would not work with the http:// URI
- Bug Fix: Collector port ranges in frontend.xml are now validated for errors
- Bug Fix: Schedd name, frontend name and identity in factory config are validated for errors
- Bug Fix: Starting a factory with all entries disabled now prints helpful message
- Bug Fix: Glidein does not leak LD_LIBRARY_PATH to job's environment
- Bug Fix: Added several speed enhancements to the factory to get looptime under acceptable limits
- Bug Fix: Fixed a bug where factory would not query rpm installed schedd correctly
- Bug Fix: Fixed a bug where factory would throw exception while logging during aggregating monitoring information
- Bug Fix: Fixed a bug where factory would fail advertising classads to the WMS Collector when classad attributes had quotes in them
- Bug Fix: Fixed a bug where glidein's condor_startd would not correctly advertise LSB_DESCRIPTION in the classad correctly
- Bug Fix: Fixed a bug where frontend would not correctly account idle jobs that used vanilla proxies
- Bug Fix: Factory now properly logs errors when authenticating a frontend
- Bug Fix: Fixed a bug in glidein where it would not report back to all the user pool collectors in HA mode correctly
- Bug Fix: Fixed a bug where some of the parameters passed to glideins were not escaped correctly
- Bug Fix: Submitting glideins in test only mode now works correctly
- Bug Fix: Fixed a bug where factory would not submit glideins when privilege separation is disabled
- Bug Fix: Fixed a bug in manageFactoryDowntimes.py where it could not find required python libraries
- Bug Fix: Fixed a bug in factory accounting where glideins in certain state were not accounted towards idle state
- Bug Fix: Added support for the ACCEPTED state for ARC CE
- Bug Fix: factoryStatus.html now correctly auto-selects timezone
- Bug Fix: Fixed a bug where RSL for NorduGrid CE was not populated
- Bug Fix: glidefactory classads now correctly display GlideinWMSVersion
- This is work in progress, so some pieces may be broken and the documentation out of sync. But it is a good place to look for what is going on.
</div>

<p>&nbsp;    
</p>


<div class="section" markdown="1">
<a name="development" />
###### Development Series
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_3_3**   
(released on April 17, 2018)
</p>
<div class="lists" markdown="1">

- Includes all features and bug fixes released in v3_2_22_2
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_3_2**   
(released on March 24, 2017)
</p>
<div class="lists" markdown="1">

- Allow multiple remote directories for BOSCO submissions
- Bug fix: Submit attributes in entry configuration are now transmitted to AWS VM
- Documented vm_id_fname and vm_type_fname
- Includes all features and bug fixes released in v3_2_18
- Includes some important features and bug fixes planned for v3_2_19 (fix of AWS submission)
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_3_1**   
(released on October 25, 2016)
</p>
<div class="lists" markdown="1">


- Includes all features and bug fixes released in v3_2_16
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_3**   
(released on August 30, 2016)
</p>
<div class="lists" markdown="1">

- Includes all features and bug fixes released in v3_2_15
- Support native configuration of EC2 spot prices and AZ in the entry
- Support Google Compute Engine CE. Requires glidein cloud vm rpms v2+
- Support frontend policies specified in external python file
- Support changes to VM ID and VM Type without need to reconfig/upgrade frontend service
- Includes all features and bug fixes released in v3_2_15
- Support Google Compute Engine CE. Requires glidein cloud vm rpms v2+
- Support native configuration of EC2 spot prices and AZ in the entry
- Support frontend policies specified in external python file
- Support changes to VM ID and VM Type without need to reconfig/upgrade frontend service
- Bug Fix: Multiple credential (eg: vm_id+vm_type) definitions now work correctly
- Bug Fix: create_condor_tarball now also includes required globus libraries from lib/condor that HTCondor loads at runtime
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_1**   
(released on August 1, 2013)
</p>
<div class="lists" markdown="1">

- Includes relevant features and bug fixes released up to v2_7
- Added a new feature that enables glidein to advertise error classAds to the User Collector to help in debugging
- Added a new tool add_entry to help with entry creation
- Support frontend to auto-update and auto-generate proxies using
- Added config conversion tool for factory and frontend to convert v2 based config to new format proxy creation tools
- Frontend can periodically execute external proxy renewal/creation scripts to keep the frontend proxies updated
- Glideinwms now uses standard python logging APIs
- Version 3 Factory is backward compatible with the Version 2 Frontends
- Provide tools convert_frontend_2to3.sh and convert_factory_2to3.sh to convert the version 2 based config files to version 3 format
- Glidein Monitoring slots are now disabled by default
- Factory process now tries to increase RLIMIT_NPROC if possible
- Improved documentation
- Bug Fix: DAEMON_SHUTDOWN now works with the multi-slot glideins
- Bug Fix: Tools analyze_queues and analyze_frontend now correctly work with the http:// URI
- Bug Fix: Fixed a bug where glidein would not parse some of its configuration variables corectly
- Bug Fix: Fixed a bug where create_glidein would fail when used with condor 7.9.4+
- Bug Fix: Factory does better error reporting when an entry is configured with an invalid schedd_name
- Bug Fix: Fixed bug where log files were not rotated correctly
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_0**   
(released on April 5, 2012)
</p>
<div class="lists" markdown="1">

- Support for new API for factory - frontend communication
- Added support to the Factory for EC2 Query API submissions to the Cloud
- Change to max job limits to reflect more accurate names
- Add attr_dict in the environment of the frontend match_expr
- New feature: The start_expr is now a native part of match
- Improved logging using standard Python logging APIs
- The option to have either the factory and/or the frontend provide the pilot proxy has been removed. The frontend must always provide it.
- Added support to the Factory for EC2 Query API submissions to the Cloud
- Consolidated the condor_tarball tag in glideinwms.xml to read in a list of os, arch, version
- Added unittests for downtime, proxy plugins, and support functions
- Miscellaenous bug fixes
</div>
<p>&nbsp;    
</p>


<div class="section" markdown="1">
<a name="old" />
###### Old Releases
<a name="old" />
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_7_2**   
(released on September 10, 2013)
</p>
<div class="lists" markdown="1">

- Bug Fix: Fixed a race condition while shutting down factory service
- Bug Fix: Fixed a bug where glidein would not set certain condor config variables correctly
- Bug Fix: Fixed a bug where analyze_queues and analyze_entries would not work with the http:// URI
- Bug Fix: Collector port ranges in frontend.xml are now validated for errors
- Bug Fix: Schedd name, frontend name and identity in factory config are validated for errors
- Bug Fix: Starting a factory with all entries disabled now prints helpful message
- Bug Fix: Glidein does not leak LD_LIBRARY_PATH to job's environment
- Bug Fix: Fixed a bug where stopFactory would send two TERM signals too quickly to stop processes
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_7_1**   
(released on May 14, 2013)
</p>
<div class="lists" markdown="1">

- glidecondor_addDN tool now supports adding DNs from a file
- Added new tool - -glidecondor_createSecCol to dynamically create secondary collectors
- Bug Fix: Fixed a bug where condor config templates used by glideinwms components had undefined values
- Bug Fix: analyze_entries tool now correctly handles URI http://
- Bug Fix: Fixed a bug where frontend would crash if the some of the internal files were truncated to zero length.
- Bug Fix: Factory now correctly does the cleanup of log files
- Bug Fix: Factory now correctly does accounting of glideins in default condor submit node (schedd)
- Bug Fix: proxy_info works correctly with the cat option

</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_7**   
(released on April 2, 2013)
</p>
<div class="lists" markdown="1">

- glideinwms code is now organized as python packages
- Factory no longer creates long running process per entry. Instead, it runs only a single long running glideFactoryEntryGroup process instead of multiple glideFactoryEntry processes. Factory config supports two additional config attributes entry_parallel_workers and update_thread_count (see factory configuration docs for details)
- Improved factory prerformance by migrating open calls to use python's subprocess library
- Improved the performance of the Frontend by using pre-clustering in the Frontend match-making
- Created index.html for factory monitoring so that admins can disable directory browsing in httpd.conf
- Added support for Partitionable condor slots in the glidein
- Frontend policy for matching factory classads is now exposed in glideresource classads
- Added a tool to dynamically create a secondary schedd config files and directories to the existing installation
- Improved the usability of the frontendGrouGraphStatusNow monitoring
- Factory now ships with two new operations tools: entry_ls and entry_rm
- Improved documentation
- Factory will now try to recover glideins with held code 79
- Bug Fix: Fixed a bug where the factory entry processes and the frontend group (element) processes would inherit their parent's environment corrupting their own environment
- Bug Fix: Fixed a bug where installers were not setting SHARED_PORT_MAX_WORKERS in respective condor_config correctly
- Bug Fix: Fixed a bug where the frontend would match jobs with now proxy to sites that require glexec
- Bug Fix: Glidein's job wrapper now behaves as true wrapper
- Bug Fix: Fixed a bug where frontend_startup would not correctly pick default frontend.xml
- Bug Fix: Fixed a bug in frontend where failure to evaluate match_expr for one group would prevent frontend from requesting glideins for other groups
- Bug Fix: RPM now has shared port daemon enabled in the configuration
- Bug Fix: Fixed a bug where Factory would sometime use wrong DN when calculating proxy hash
- Bug Fix: Fixed a bug where factoryStatusNow.html would not link to the factoryEntryStatusNow.html correctly if the entry name is too long
- Bug Fix: setup_x509.sh now correctly checks for existence of the grid-proxy-info and voms-proxy-info binaries on the worker node
- Bug Fix: Frontend now counts the partitionable slots correctly
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_6_2**   
(released on November 2, 2012)
</p>
<div class="lists" markdown="1">

- Factory now supports glidein failure modes. This information is propagated back to the factory.
- Glideins now have different idle timeouts for startup and tail. The glideins now exit much faster after comleting jobs and they do not have enough time left to run another job.
- Added support for javascriptRRD 2.6.2
- Consolidate the condor_tarball tag in glideinwms.xml to read in a list of os, arch, version. See docs for details.
- Ini-installer will default collector_port to 9618 if not specified in appropriate config sections.
- Installation now supports GRIDMANAGER_PROXY_REFRESH_TIME for condor services
- Improved logging when frontend fails to evaluate match expressions.
- Monitoring pages changed to be even more compliant with DOM4
- Improved the means for distributing condor config files for different condor services.
- Improved documentation.
- Bug Fix: Better handling of monitor dir during upgrade
- Bug Fix: Factory correctlt handles frontend in downtime and now it does not affect requests from other frontends
- Bug Fix: Putting entry in downtime multiple times now warns the user
- Bug Fix: Fixed a bug where v2.6.1 frontend would crash under certain
- Bug Fix: Installers do not set CONDOR_VERSION as constant by default. This will now enable frontends to override this attr.
- Bug Fix: Ini-installer now correctly cleans up files on re-install
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v3_0**   
(released on August 21, 2012)
</p>
<div class="lists" markdown="1">

- NOTE: Follow special instructions on downloads page if upgrading to condor 7.8.2

- Factory now limits the speed at which it releases held glideins. After too many unrecoverable attempts, held glideins are removed.
- Added support for Condor 7.8+
- KNOWN ISSUE: Only applies if you upgrade condor binaries in place without using the installer. Upgrading condor binaries for user pool and the wms collector with multiple schedds should not be done without corresponding changes to the condor configuration file. If the JOB_QUEUE_LOG is not correctly configured for each schedd, condor queue will be corrupted for all the schedds
- Glideins now support curl & data file transfer plugins in condor
- New installations of factory and frontend services now communicate with condor daemons using TCP by default.
- Bug Fix: Factory configuration now supports specifying limits for different security classes of same frontend
- KNOWN ISSUE: If limits are configured in the factory, this change breaks backward compatibility. As a workaround, admin needs to remove the limits and re-apply them after installation and initial configuration
- Bug Fix: Factory monitoring pages now correctly work in Firefox 14+
- Bug Fix: Frontend now monitors the glideins correctly when the corresponding factory classad is missing
- Bug Fix: Fixed factory logging. Factory can now correctly extract info from a voms proxy
- Bug Fix: Factory now correctly logs the Completed jobs info in rrd
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_6**   
(released on July 24, 2012)
</p>
<div class="lists" markdown="1">

- Add attr_dict in the environment of the frontend match_expr
- Config defined attributes are now available in match_expr
- Factory now supports deleting entries using --force_delete
- Upgrading glideinwms with changes to the monitoring rrds is supported
- Frontend advertises its monitoring url to the factory
- Misbehaving glidein can be put on hold using WANT_HOLD
- The start_expr is now a native part of match
- Startd now advertises per-slot memory when configured by the factory. VO frontend can use GLIDEIN_MaxMemMBs_Estimate attr to make glidein estimate the available memory (based on memory/core or memory/cpu)
- entry_q now reads GLIDEIN_FACTORY_DIR from env before checking cwd
- Multiple user collectors are supported in HA mode
- Factory can specify if glexec required vs provided by site
- Providing config file locations for glideinwms.xml and frontend.xml is optional during reconfig
- Entry downtime reason is now reported in the glidefactory classad
- Improved support for RHEL 6 platform
- Added support for new ARC Gatekeeper 1.x
- Linux distro of the worker node is available in the glidein's classad
- Condor classad fields are now considered case insensitive
- Bug Fix: Glidein correctly handles semicolons in STARTER_JOB_ENVIRONMENT
- Bug Fix: Java is correctly disable by default preventing increase in the image size during condor daemon benchmarking
- Bug Fix: Frontend correctly correctly supports properties
- Bug Fix: Glidein now correctly finds glexec on glite site
- Bug Fix: Glideins update the user collector using TCP by default
- Bug Fix: Ini-Installer now correctly works with condor tarball on RHEL6
- Bug Fix: Reduced the logging in factory generated by inactive entries
- Bug Fix: For frontend rpm, init.d scriptes now correctly sudo to the frontend user before reconfig
- Bug Fix: Any errors due to changes in condor_q output are logged
- Bug Fix: MaxJobRetirementTime and PREEMPT expressions now correctly work with WANT_HOLD
- Bug Fix: Factory correctly deals with the situation when the frontend changes the proxy used
- Bug Fix: It is possible to specify limits for different frontends for an entry in the factory config
- Bug Fix: Glidein sets the LD_LIBRARY_PATH so condor uses local shared libraries before those in system path
- KNOWN ISSUE: When the monitor work_dir is moved, reconfig/upgrade will fail. Recommended work-around is to delete the xml configuration in the work directory, change the work directory, then reconfig/upgrade.
- KNOWN ISSUE: If the work directory has changed, frontend startup upgrade will not create the group directories and then the frontend will fail (silently). If you are changing directories (e.g. from a RPM upgrade), you should copy the group directories manually.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_7**   
(released on April 5, 2012)
</p>
<div class="lists" markdown="1">
- Patch of the clean_glidein_queue to return 1 only when something was really done
- Fix handling of held jobs when hitting the held limit
- Fix log messages that printed out wrong held limits
Add locking when talking to the collector
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_6**   
(released on March 16, 2012)
</p>
<div class="lists" markdown="1">

- Factory supports per-frontend limits in the config
- Bug Fix: Fixed a bug where frontend would not stop cleanly
- Bug Fix: Factory does not depend on the X509_CERT_DIR in the environment
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_5**   
(released on February 10, 2012)
</p>
<div class="lists" markdown="1">

- Added filtering to analyze_entries
- Reduced the number of debug log messages when entry becomes inactive.
- Frontend match making uses autoclusters, greatly increasing the performance for busy frontends
- Package the list of shared libraries required by Condor 7.7.3+ for glidein tarballs
- Pilot proxy is not available in the user job environment any more reducing the chance for user job using it.
- Ini Installer caan now create a template for single service installs
- Bug Fix: Fixed several issues with the frontend rpm
- Bug Fix: GLIDEIN_Glexec_Use=NEVER setting now correctly works with the setting require_voms_proxy=True
- Bug Fix: Installer now correctly works with the RPM OSG client
- Bug Fix: ReqMaxIdle was grossly overestimated before.
- Bug Fix: Fixed bug in factory monitoring web pages where the link generation was off by one for monitoring groups
- Bug Fix: Correctly respect the remove max_per_cycle=0 glideins in the factory
- Bug Fix: glexec_setup.sh now uses correct proxy for its tests
- Bug Fix: "warn" function is defined in generated add_config_line.source
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_4**   
(released on December 19, 2011)
</p>
<div class="lists" markdown="1">

- NOTE: To upgrade to this version from anything earlier than v2.5.3, please see the instructions here.
- Added support for VDT pre installed via rpm. While using ini-installer set vdt_location to empty and x509_cert_dir=/etc/grid-security/certificates
- Consolidated some of the frontend rpm related patches
- Added support for rsl in glideinWMS.xml to map to cream_attributes in the jdf
- Bug Fix: Factory now correctly renews the proxies if the limits are hit
- Bug Fix: frontend_startup does not show "upgrade" in help
- Bug Fix: glideclient, glidefactoryclient and glideresource classads now correctly show UpdateSequenceNumber to help condor track potentially lost updates
- Bug Fix: Fixed a bug where condor_shared_port daemon was not correctly stopped under certain conditions

</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_3**   
(released on November 11, 2011)
</p>
<div class="lists" markdown="1">

- NOTE: To upgrade to this version from anything earlier than v2.5.3, please see the instructions here.
- Updated the license to reflect current Fermitools license Factory does a better job at respecting frontend limits Admins can add custom html to the monitoring pages
- Monitoring now displays additional information about the Factory and Frontend names
 - Improved documentation
- Enable Match Authentication configuration by default
- Made quering of submit nodes (schedds) efficient wherever possible.
- Add autocomplete/search to table in frontendGroupGraphStatusNow.html
- Added 'upgrade' option to factory startup script so that all the files in the glidein submit directory are updated. Did the same for the frontend startup script. 'reconfig' only updates the files populated with information from the configuration files (no scripts).
- The OSG rpm worker node client requires changes to glidein startup scripts. If you plan on using OSG sites that have used this rpm, you must "upgrade" your factory in order to get glideins.
- Bug Fix: If there is no GLOBUS_LOCATION available to glidein, it will not exit
- Bug Fix: Fixed a bug where factory would not advertise the entry under certain conditions when it was put in downtime.
- Bug Fix: Fixed a bug where glidein_reconfig would not properly validate schedd_name
- Bug Fix: Fixed a bug where frontend reconfig was not populating GSI_DAEMON_PROXY correctly in frontend.condor_config
- Bug Fix: Writeback of config files on reconfig is now enable by default
- Bug Fix: Frontend does better error reporting when quering user pool or the schedd fails
- Bug Fix: Fixed a bug in condor log parsing when we encounter event 400 (Job was evicted)
- Bug Fix: Fixed a bug where factory would not correctly accept requests from frontends that were still using old keys
- Bug Fix: Fixed a bug where glidein pilot proxy lifetime was not taken into account vs GLIDEIN_Max_Walltime
- Bug Fix: Fixed a bug where expired/renewed proxy created error in completed_jobs accounting
- Bug Fix: Fixed a bug where running_glideins_per_entry was not treating the limits correctly
- Bug Fix: Fixed a bug in DAEMON_SHUTDOWN
- Bug Fix: Fixed a bug where voms requirements were not treated correctly
- Bug Fix: Added glidecondor_upgrade back to the install dir. This file was missing in v2_5_2_1 release
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_2_1**   
(released on October 7, 2011)
</p>
<div class="lists" markdown="1">

- Bug Fix: Fixed a bug creation of START expression when VOMS proxy is set be required.
- Bug Fix: Revert the glidein shutdown behavior introduced in v2_5_2
- Bug Fix: Add condor_glexec_update_proxy to Condor tarball if available
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_2**   
(released on July 20, 2011)
</p>
<div class="lists" markdown="1">

- Frontend publishes glideresource classad to the pool collector. This is useful for the users to do match making for their jobs.
- Useful job info like JOB_Site, JOB_GLIDEIN_Entry_Name, JOB_GLIDEIN_Name JOB_GLIDEIN_Factory, JOB_GLIDEIN_Schedd, JOB_GLIDEIN_ClusterId, JOB_GLIDEIN_ProcId, JOB_GLIDEIN_Site is now added to SUBMIT_EXPRS
- Default GLEXEC_JOB = True when GLEXEC_BIN is set to use glexec
- Factory can now resue old public key after startup to decrypt frontend requests. Grace time for old public key is configurable.
- The frontend now can set global limits on number of glideins.
- The frontend now can use more than a single CPU.
- glexec now tested during initial validation.
- Bug Fix frontend: Do not double count glideins when using multiple groups.
- Bug Fix frontend: Respect per-entry running limits.
- Bug Fix factory: The factory was not properly checking the security classes and setting downtimes.
- Bug Fix factory: Improper termination of glideins because of SIGHUP is handled correctly
- Bug Fix factory: Daylight savings is now correctly accounted for.
- Bug Fix factory: GLIDEIN_Max_Walltime is now used correctly.
- Major improvements in the factory and frontend monitoring. Now requires javascriptRRD 0.6.0+.
- Added tools for comparing the Factory configuration file with what is published in information systems.
- Limit the max number of glideins per frontend
- Use DAEMON_SHUTDOWN to shutdown glidein daemons
- Allow factory to specify if an entry point (CE) requires voms proxies only for pilot and user jobs
- Documentation Improvements:
- Secondary WMS/User Collector documentation added to Advanced Condor Configuration
- Documented the internal communication protocol through classads
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5_1**   
(released on March 2, 2011)
</p>
<div class="lists" markdown="1">

- Factory now can remove excessive glideins. New ClassAd attribute - RemoveExcess
- Frontend will request removal of glideins when no user jobs in queue
- Improved idle counting by the frontend when jobs match many factory entries.
- Improved frontend logging.
- Add Java support in the glideins.
- Changed factory monitoring. It is now based on security names and not plain frontend names
- Improved installation process using ini based installer.
- GlideinWMS tarball does not include CVS directories and files any more
- Added support of shared port configuration for condor daemons
- SIGHUP signals to glideins are ignored correctly.
- Improved documentation
- Bug Fix: Fixed a bug introduced in v2_5 release where reconfiguring the factory would fail because of monitoring groups
- Bug Fix: Fixed a typo in one of the links in frontendRRDBrowse.html
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_5**   
(released on January 24, 2011)
</p>
<div class="lists" markdown="1">

- Installer can now install gridFTP and VOMS certs needed by CREAM
- glideinWMS release is now available in 3 different tarballs, frontend only, factory only and a complete tarball.
- glideinWMS factory and the Corral frontend can now talk to each other
- Factory is smarter about handling held glideins
- Factory can now black/white list VOs on a per-entry basis
- Version of glideinWMS is now published in the classads. Scheme can detect any changes to any service appropriate files and advertises version as patched.
- Frontend should try to recover the crashed group before it gives up and shuts down
- Improvements to the monitoring
- Improvements to documentaion
- Add support for use of TCP in condor_advertise
- Add support for condor_advertise -multiple (requires Condor v7.5.4+)
- Improved factory stopping procedure
- Add XML monitoring files of RRD files on both factory and frontend
- Add JobsRunningHere attribute - CANNOT SIMPLY UPGRADE, NEEDS NEW INSTANCE FOR BOTH FACTORY AND FRONTEND
- Graceful shutdown of the glidein by trapping signals in glidein_startup
- BUG FIX: Fixed a bug where factory would create a malformed glideinWMS.xml config file when configured to use a default proxy for glideins from the factory.
- BUG FIX: Factory entry sometimes stops reporting when it gets an exception for any reason
- BUG FIX: Top-level schedd_status.xml malformed Total data
- BUG FIX: Fixed a bug where the LogCounts.rrd was created with wrong data types.
- KNOWN ISSUE: Automatic release of held glideins for CREAM CEs with issues could result in factory submitting more than required glideins to the CE. As a workaround, disable release of held glideins for CREAM CE.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_4_3**   
(released on September 30, 2010)
</p>
<div class="lists" markdown="1">

- Install VOMS Certificates during the install time
- Entry does not print stacktrace when it fails to submit glidein. Instead, it logs the error message appropriately.
- Default scripts run on the worker node correctly print errors to stderr instead of stdout
- Allow factory to startup from any directory
- Python scripts get the python from /usr/bin/env python instead of /bin/env python making them more portable accross different linux distros
- Better exception handling and error reporting
- Fixed how voms_proxy_init is looked for after VDT install
- BUG FIX: Fixed a bug where Summarize.listStored() in CondorMonitor.py returned the wrong value
- BUG FIX: Fixed a bug in factory monitoring that prevented proper aggregation of sites
- BUG FIX: Correctly interpret DN from a voms proxy generated from a service certificate.
- BUG FIX: Generate frontend's condor_config without empty values for certain configuration options. Empty values is not the right way to reset the configuration options.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_4_2**   
(released on August 3, 2010)
</p>
<div class="lists" markdown="1">

- Fixed the incompatibility introduced in v2_4_1 in monitoring components.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_4_1**   
(released on July 27, 2010)
</p>
<div class="lists" markdown="1">

- Add a new configuration option for PREEMPT_GRACE_TIME
- Move configuration of GLIDEIN_Job_Max_Time from the factory to the frontend
- In factory config added checks to make sure Factory configuration is consistent w.r.t CONDOR_ARCH, CONDOR_VERSION, CONDOR_OS
- Monitoring enhancement to make selection/deselection of groups/entries easier
- Support GLIDEIN_Glexec_Use in frontend config attrs. Frontend can mandate or make the use of GLEXEC optional. Used in conjunction with GLEXEC_BIN in factory config. If GLEXEC_BIN in set to NONE for an entry in factory config, it is assumed that the entry doesn't have GLEXEC configured on site.
- Improvements to documentation
- BUG FIX: Allow the use of the same DN for both the security and the collector
- BUG FIX: Returning invalid variable during proxy creation
- KNOWN ISSUE: Running glideinWMS
 - v2_4_1 with Condor 7.5.3 has not been tested. Altough, most of the things may work, security changes in Condor may affect your installation.
- KNOWN ISSUE: Installer is not always able to get the correct DN from the certificates/proxies. It does not correctly strip the CN=>blah< bit of the DN in certain cases. If the DN guessed is not correct, make the required changes in the configurations and/or condor_mapfile.

</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_4**   
(released on May 4, 2010)
</p>
<div class="lists" markdown="1">

- Add proxy security classes to the frontend
- Add SecurityName to the frontend.
- Add DNs for frontend proxy and all the daemons the frontend talks to; create own Condor config file and gldiein gridmap file out of them.
- Frontend now dynalically creates GLIDEIN_Collector.
- Frontend now requires Match authentication.
- Add frontend autentication info to the factory config.
- Add support for different frontend identities in different WMS collectors.
- Put log files in a separate tree.
- Put client logs and client proxies in separate trees.
- Implement privilege separation in the factory.
- Various minor refactoring of code to achieve the above.
- Aggregate gatekeeper/sites for factory monitoring.
- Introduced monitoring groups to group sites together for monitoring purposes in factory.
- KNOWN ISSUES: Installer is not always able to get the correct DN from the certificates/proxies. It does not correctly strip the CN=>blah< bit of the DN in certain cases. If the DN guessed is not correct, make the required changes in the configurations and/or condor_mapfile.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_3_2**   
(released on April 6, 2010)
</p>
<div class="lists" markdown="1">

- Fixed a security bug in the way certificate/proxy DN(s) are handled. If you are upgrading the installation rather than full install, you should patch the condor_mapfile used by Condor daemons in your installation using the convert_condormap tool available from the glideinWMS download page. For additional security, users should add new DN to the condor_mapfile only by using the glidecondor_addDN tool available in the glideinWMS/install directory.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_3_1**   
(released on March 11, 2010)
</p>
<div class="lists" markdown="1">

- Documentation Changes. There are no code changes since v2_3.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_3**   
(released on February 2, 2010)
</p>
<div class="lists" markdown="1">

- Current development version.
Improvements list:
- Attempt to restart a crashed -entry few times before shutting down the factory. Restarting is allowed for max restart_attempts in time interval restart_interval sec in te factory.
- Add vacuum option to manageDowntimes.
- Factory now properly handles new-style frontends without a group.
- Frontend code has been refactored to allow use as a library.
- More protections in place.
- Fixed a security bug in key handling. BREAKES BACKWARDS COMPATIBILITY! But it is needed.
- Fixed a bug in glidein_startup.sh that prevented the passing of * as a parameter value
- Fixed a logical bug in the glidein config that resulted in job preemption.
- Added support for condor_ssh (v7.4 and up)
- Add support for unquoted string to be published in classads. The type is 'expr'
- Documentation Changes
- Minor bugs fixed.

KNOWN ISSUES: If using condor 7.4.0-7.4.2 and 7.5.0, USE_VOMS_ATTRIBUTESshould be set to false for Collector and negotiator to avoid potential problems and memory leaks in GSI libraries.
WARNING: This release has security bug fixes and is not compatible with older releases. You will need to update all the daemons at the same time.

</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_2**   
(released on November 3, 2009)
</p>
<div class="lists" markdown="1">

Current development version.
Improvements list:
- Bug Fix: GLEXEC_JOB and GLEXEC_STARTER were not published in glideins classds. This was preventing psuedo interactive monitoring to work in case of GLEXEC.
- Made VDT optional.
- Added support for VDT 2.0, and made it the default.
- Added Globus-Client and Myproxy-Client in the minimal VDT install.
- Installer now allows the collector to run on non-standard port.
- Factory now only checks X509_USER_PROXY if it needs it.
- Added support for multiple versions of condor in a single factory.
- Added ReqEncIdentity to the frontend->factory protocol to prevent replay attacks.  

- WARNING: This effectively prevents old-style frontends to talk to new style factories.
- NOTE: Will only work with Condor 7.3.1 or newer
- KNOWN ISSUES: Pseudo interactive monitoring will not work with glexec.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_1**   
(released on August 24, 2009)
</p>
<div class="lists" markdown="1">

Improvements list:
- Fixed a bug that was throwing an exception if a glidein failed.
- Fixed handling of grid-mapfiles coming from client.
- Fixed support for nordugrid.
- Improvements to the monitoring.
- Improvements to the installer.
- Improved documentation.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v2_0**   
(released on March 5, 2009)
</p>
<div class="lists" markdown="1">

Improvements list:
- create_frontend and create_glidein now share much code
- Added create_frontend, recreate_frontend.
- Frontend now has a stage web area and passes it to the factory
- Factory publishes list of supported signtypes and frontend uses this for factory selection
- User provided code in the glidein API changed. The 2nd arg is now one of
main l entry l client l client_group
- Added tools/glidein_status.py.
- The monitoring page now has client-side monitoring based on javascriptRRD.
- Support multiple proxies... frontend drives this via plugins.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_6_3**   
(released on April 6, 2010)
</p>
<div class="lists" markdown="1">

- Fixed a security bug in the way certificate/proxy DN(s) are handled.  
If you are upgrading the installation rather than full install, you should patch the condor_mapfile used by Condor daemons in your installation using the convert_condormap tool available from the glideinWMS download page. For additional security, users should add new DN to the condor_mapfile only by using the glidecondor_addDN tool available in the glideinWMS/install directory.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_6_2**   
(released on September 14, 2009)
</p>
<div class="lists" markdown="1">

- Current production version.
- Minor bug fixes.
- Systems that installed v1.6.1 need to upgrade to this release. They only need to replace the glideinWMS files.

Improvements list:  

- Fixed a bug in frontend that would lead frontend to crash in certain conditions while logging the information
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_6_1**   
(released on September 8, 2009)
</p>
<div class="lists" markdown="1">

- Current production version.
- Minor bug fixes.
- Most systems don't need to upgrade.

Improvements list:

- Better randomization of GCBs and collectors
- Collector list now supports ranges of ports
- Fixed Condor-G log parsing
- Better treatment of multiple-collectors in the installer
- Add support for CCB and USE_MATCH_AUTH in the installer.
- Add OSG:vo-client to the minimal VDT install
- Better handling of Nordugrid sites.
- Start factory in nice mode to give priority to Condor daemons
- In condor_config for glideins remove explicit STARTER_UPDATE_INTERVAL
- Removing GLIDEIN_Use_TCP, now uses UPDATE_COLLECTOR_WITH_TCP instead
- Force integrity on reads from WMS collector
- Better layout of monitoring pages
- Better error handling in Factory downtime management
- Better formatting of error logs for factory and frontend
- Bug Fix: GLEXEC_JOB and GLEXEC_STARTER were not published in glideins classds. This was preventing psuedo interactive monitoring to work in case of GLEXEC
- Improved documentation
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_6**   
(released on March 5, 2009)
</p>
<div class="lists" markdown="1">

- Current production version.
- Improved scalability, improved documentation and minor bug fixes.
- Added dependency on m2crypto.
- Most systems don't need to upgrade.

Improvements list:

- The XML file now supports comments.
- Installer uses both .profile and .bashrc.
- Frontend now requires integrity checks when talking to the WMS collector.
- Refactored install options so that most tasks performed as a non-privileged user.
- Using m2crypto for sha1 checks.
Fixed startup bugs in various debug tools.
- Improved monitoring scalability (fewer RRD files)
- Add support for CCB.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_5_2**   
(released on November 6, 2008)
</p>
<div class="lists" markdown="1">

- The major new feature is a fix for VDT installation.
- Most systems don't need to upgrade.
Improvements list:
- Fixed VDT installation.
- Factory now changes public key at each restart.
- Minor monitoring improvements.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_5_1**   
(released on October 28, 2008)
</p>
<div class="lists" markdown="1">


- This is essentially a bug fix release for v1_5.
- It is safe to upgrade.
Improvements list:
- Added flag that allows/requires proxies from frontend.
- Fixed bug in factory installation with encryption.
- The glidein now finds out about OSG squid.
- Fixed bug in the node blacklisting code.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_5**   
(released on October 24, 2008)
</p>
<div class="lists" markdown="1">

- Contains several scalability features over v1_4_X.
- Contains a new secure message passing infrastructure.
Improvements list:
- Added support for secure info passing between VO frontend and gfactory
- Requires M2Crypto Python module
- VO frontend can now give the gfactory its own proxy to be used for pilot submission
- Requires the encryption mentioned above
- gcb_setup is now loaded by default
- Can use GCB_ORDER=NONE to disable it
- Warning: Explicit listing of gcb_setup may create problems.
- glexec_setup is now loaded by default
- Can use GLEXEC_BIN=NONE to disable it
- Warning: Explicit listing of glexec_setup may create problems.
- Randomized the retire time to smooth terminations.
- Can be controlled via GLIDEIN_Retire_Time_Spread.
- Some monitoring tweaks.
- Added more switches
- Warning: xml slightly incompatible with v1_4_X
- The factory config file is now read only.
- Added switches to limit log file growth.
- Warning: If upgrading from v1_4_X, the reconfig will fail due changes in the monitoring setup. Manually remove want_split_terminated_graphs switch in the XML file and the reconfig will work again.
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_4_4**   
(released on September 30, 2008)
</p>
<div class="lists" markdown="1">

- This is a bug fix and condor update release, and you are encouraged to upgrade from v1_4_3.
Improvements list:
- Add factory_constraint parameter to the frontend.
- Add support for GLEXEC_JOB.
- Add support for USE_MATCH_AUTH.
- Add new protection against condor_submit errors.
- Warnings go into the info file, too. Easier to correlate errors this way.
- Better colors in graphs.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_4_3**   
(released on September 5, 2008)
</p>
<div class="lists" markdown="1">

- This is a scalability release, and you are encouraged to upgrade from v1_4_2.
Improvements list:
- Added mutexes to reduce factory load due to monitoring.
- Previous releases were not really scalable to more than approximately 50 entry points.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_4_2**   
(released on August 26, 2008)
</p>
<div class="lists" markdown="1">

- This is a bugfix release, and you are encouraged to upgrade from a v1_4_1.
Improvements list:
- Improved pseudo-interactive monitoring
- The changes introduced in v1_4_1 could leave behind zombies.
- Fix glexec setup script bug.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_4_1**   
(released on August 13, 2008)
</p>
<div class="lists" markdown="1">

- It is safe to upgrade from a v1_4.
Improvements list:
- Improved pseudo-interactive monitoring
- By default use a separate startd for montoring
- Old multi-VM mode can be enabled by MONITOR_MODE=MULTI
- Fixed factory handling held jobs
- Improved installer defaults
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_4**   
(released on August 7, 2008)
</p>
<div class="lists" markdown="1">

Improvements list:
- Better support for RESS and BDII
- Including automatic downtime handling
- User STARTD_SENDS_ALIVES=True by default.
- Disable glidein UDP port by default.
Note: This affects how Condor works
- Global files can now be loaded after entry
- Added support for job wrapper scripts.
- Fix monitor locking.
- gcb_setup now supports ORDER=NONE.
- gcb_setup is now loaded automatically.
- Add verbosity to entries.
- Add config section to entries.
- Improve held handling.
- Add a completed job log.
- Improve signal handling (for stopping frontend/factory)
- Made the most CPU intensive part of monitoring optional.
- Installer now supports multiple collectors.
- WARNING: If you used a previous version, consider reinstalling everything, including Condor.
- This version contains several key changes.
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_3**   
(released on July 17, 2008)
</p>
<div class="lists" markdown="1">

Improvements list:
- Factory and frontend now gets sleep and advertize attr from config.
- Add downtime concept to the factory and relative management tool.
- Add command to get info about factory config file.
- Add init.d style startup script.
- Fix pseudo-interactive monitoring when glexec is used.
- Reduce VO frontend condor_q load by adding job_attributes.
- VO frontend now queries the collector and advertises result.
- Smarter algorithm to calculate min_idle, also using condor_status.
- Improve monitoring.
- Minor bug fixes.
- WARNING: Entry points need to be recreated, if you used an older version.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_2_3**   
(released on July 2, 2008)
</p>
<div class="lists" markdown="1">

Improvements list:
- Fix glexec handling in condor v7.0.2 and above.
- Cut in half the number of condor_q's in the frontend.
- Minor monitoring twaeks.
- Minor installation tweaks.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_2_2**   
(released on June 27, 2008)
</p>
<div class="lists" markdown="1">

- This version fixes a major installer bug and has monitoring over v1_2_1. It is safe to upgrade from a v1_2_1, however, the entry points need to be recreated.
Improvements list:
- Fix condor installation.
- Update versions in installer.
- Added glidein_gcb and collector_setup.
- Add LIBEXEC to condor_config.
- Better support for EGEE (by supporting $TMPDIR).
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_2_1**   
(released on May 30, 2008)
</p>
<div class="lists" markdown="1">

- This version has essentially usability and monitoring improvements over v1_2. It is safe to upgrade from a v1_2.
- The major improvements are:
- Added support for BDII.
- Added stop scripts for factory and frontend.
- Added tools/wmsTxtList.py and tools/glidein_interactive.py.
- All commands now are executable.
- Add client and Condor-G monitoring in factory data.
- Greatly improved log stats monitoring.
- Add doc section on monitoring.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_2**   
(released on May 5, 2008)
</p>
<div class="lists" markdown="1">

It has several improvements over v1_1, including:
- More fine grained configuration of glideins
- Factory reads now force integrity checks
- Glideins now publish the gatekeeper name
- Fixed several bugs
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_1**   
(released on January 30, 2008)
</p>
<div class="lists" markdown="1">

It has several improvements over v1_0, including:
- Entry points can now be updated by using reconfig_glidein
- Add automatic OSG glexec discovery
- Use condor_mapfile for authorization
- Installer now supports Condor v7 (without Quill)
- Installer now supports gLExec
- Fixed several minor bugs
WARNING: Security configuration has been overhauled to fix the security issues of the provious verisons.
- Please reinstall (or at least reconfigure) your Condor installation.
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v1_0**   
(released on December 18, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_9, including:
- During installation, Quill is now optional.
- During installation, Condor config can be split into condor_config.local.
- Files are now loaded in order specified.
- Added local_start.sh to ease testing.
- create_glideins code had a major rewrite, but users should not notice any major change.
- Slimmed down glidein_submit.sh.
- Many bugs fixed.
WARNING: Entry points need to be recreated, if you used an older version.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_9**   
(released on Novemebr 14, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_8, including:
- Significant speedup in the VO frontend matchmaking
- Added MaxRunningGlideins request
- Use human readable dates in logs
- Factory will use python rrd module if present
- Reduced graphing load of the factory
- Frontend will work even if some of the schedd are down
- Improved installation scripts.
WARNING: The config directory structure has changed a lot for both the factory and the frontend and need to be recreated, if you used an older version.
</div>
<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_8**   
(released on May 24, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_7, including:
- Add support for multiple schedds
- Add initial support for pseudo interactive monitoring
- Improved Web monitoring
- Better documentation
WARNING: The config directory structure has changed a lot and need to be recreated, if you used an older version.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_7**   
(released on April 11, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_6, including:
- Add support for Condor 6.9.2.
- Add support for user variables
- Move log and monitoring files into entry dir.
- Add lock files.
- Create proper ClassAd cleanup when daemons exit.
WARNING: The config directory structure has changed a lot and need to be recreated, if you used an older version.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_6**   
(released on April 9, 2007)
</p>
<div class="lists" markdown="1">
- The glidein factory was extensively reworked:
- A single factory daemon now can serve several entry points.
- The config file is XML based.
WARNING: The config directory structure has changed a lot and need to be recreated, if you used an older version.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_5**   
(released on March 23, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_4, including:
- Several bugs has been fixed
- Improved glidein factory monitoring.
- Added monitoring information in the ClassAds.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_4**   
(released on February 12, 2007)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_3, including:
- Several bugs has been fixed
- The glidein factory now has an extensive graphical monitoring.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_3**   
(released on October 31, 2006)
</p>
<div class="lists" markdown="1">

It has several improvements over v0_2, including:
- Several bugs has been fixed
- It now supports GCB for WAN deployments and gLExec to comply with Grid site accounting
- It is now much more stable and has better logging.
- The user documentation has been greatly improved and now describes advanced configuration options, too.
</div>

<p>&nbsp;    
</p>
<p class="noheading" markdown="1">
**v0_2**   
(released on October 9, 2006)
</p>
<div class="lists" markdown="1">

- The first usable version

</div>
