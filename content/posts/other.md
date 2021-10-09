+++
title = "Viper - Go configuration with fangs"
date = "2021-09-27T23:19:35+07:00"
author = "duclm"
authorTwitter = "duclm2609" #do not include @
cover = ""
tags = ["golang"]
keywords = ["go", "golang"]
description = "Viper is a complete configuration solution for Go applications including 12-Factor apps. It is designed to work within an application, and can handle all types of configuration needs and formats."
showFullContent = false
+++
Kevin Wylie is a Data Engineer on the Content Data Science and Engineering team. In this post, Kevin talks about his extensive experience in content analytics at Netflix since joining more than 10 years ago.
Kevin grew up in the Washington, DC area, and received his undergraduate degree in Mathematics from Virginia Tech. Before joining Netflix, he worked at MySpace, helping implement page categorization, pathing analysis, sessionization, and more. In his free time he enjoys gardening and playing sports with his 4 kids.

```go
package main

import (
	"flag"
	"github.com/spf13/pflag"
)

func main() {

	// using standard library "flag" package
	flag.Int("flagname", 1234, "help message for flagname")

	pflag.CommandLine.AddGoFlagSet(flag.CommandLine)
	pflag.Parse()
	viper.BindPFlags(pflag.CommandLine)

	i := viper.GetInt("flagname") // retrieve value from viper

	// ...
}

```