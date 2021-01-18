# PoC Shared Spring Wab with Liferay 7.3

## Overview

*Foreword: This is based on https://github.com/sammso/spring-portlet-example but commit history cleaned for clarity. Huge thanks for https://github.com/mir333 for initial work*

### The goals

1. Have two Spring (4.2 and 4.3 ) frameworks to sharedly deployed to Liferay DXP / CE 7.3 and those would be then would use shared Spring bundle. - **WORKING**
2. Use OSGi subsystem to prevent other portal applications to see the modules of these Spring applicaitions. - **INCOMPLETE**


## Compile

```
mvn clean package
```

# Install

The subsystem has to be installed to your Liferay DXP 7.3 or CE 7.3

See instructions at : https://github.com/sammso/osgiray-subsystems-test

Then compile and after that do the installation from gogo shell:

```
subsystem:install file:< this project directory >/osgiray-spring-ft-feature-esa/target/org.osgiray.springmvc.ft.esa.feature-1.0.0.esa
subsystem:install file:< this project directory >/osgiray-spring-fs-feature-esa/target/org.osgiray.springmvc.fs.esa.feature-1.0.0.esa
```

See all installed:

```
subsyste:list
```

Start the subsystem with:

```
subsystem:start <subsystem id>
```
