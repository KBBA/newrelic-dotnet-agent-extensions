New Relic .NET Agent Extensions
================================

Extensions that work with the [New Relic .NET Agent](https://docs.newrelic.com/docs/dotnet/new-relic-for-net) that will give you more information on various frameworks and modules that can be used with the .NET framework.

To learn how to make these extensions you can go [here](https://docs.newrelic.com/docs/dotnet/dotnet-agent-custom-metrics), then submit a [pull request](https://github.com/nickfloyd/newrelic-dotnet-agent-extensions/pulls) and I'll add them here to help everyone out.

How to use these extensions
================================

If you installed New Relic on your [own metal](https://docs.newrelic.com/docs/dotnet/new-relic-net-installation) or if you used the [Nuget packages](https://docs.newrelic.com/docs/dotnet/installing-the-net-agent-on-azure) the process for adding extensions to what is instrumented is pretty much the same.

1. [Create an extension file](https://docs.newrelic.com/docs/dotnet/dotnet-agent-custom-metrics), [fork this repo](https://help.github.com/articles/fork-a-repo), or just grab whatever is interesting from the [source](https://github.com/nickfloyd/newrelic-dotnet-agent-extensions) in this repo.
2. Navigate to where New Relic is installed (either on your server, locally if you've installed it on you dev machine or if you used the nuget package you'll have a NewRelic folder in your source directory.
3. Place your extension (xml) file in the extensions directory (there should already be a coreinstrumetnation.xml file currently in that directory - don't overwrite that one just make sure your's has a different / meaningful name).
4. Restart your application and you should be good to go.

Notes
================================
* The more method "tracers" you add the more your application will be instrumented. You app will eventually take a performance hit if you throw in too many custom instrumentation points.  While I have not attempted to instrument everything in the .net framework (yet ;)) just try a few things and see what works for you.

* If your extension file does not work out initially try the [troubleshooting tips](https://docs.newrelic.com/docs/dotnet/dotnet-agent-custom-metrics#troubleshooting) or use [this amazing tool](http://pablissimo.com/projects/nrconfig-automatic-new-relic-custom-instrumentation-file-generation) that will generate custom instrumetnation extensions for you.

* You can always reach out to me on the [Twiters](https://twitter.com/nickfloyd) and chat about how to do this as well.


Contribute
===========================


Standards
---------------------------------
* Follow the details [here](https://docs.newrelic.com/docs/dotnet/dotnet-agent-custom-metrics) when generating the instrumentation
* Name the instrumentation file with the following convention: thing_instrumentation.xml where thing is the framework, library, etc that is being instrumented.
* Place it in the corresponding folder that is applicable for the instrumentation. For instance:  If you're doing MemcacheD then put MemcacheD_instrumentation.xml in the "NoSql" folder

Collisions
--------------------
As will many really great things others might have already solved or have started creating instrumentation for something you'd like as well check to see if there is already an instrumentation file for the thing you need.  If it does not quite "get you there" then you can always generate a [pull request](https://github.com/nickfloyd/newrelic-dotnet-agent-extensions/pulls) that adds what you need.


Pull requests
--------------------
1. [Fork the repository](https://help.github.com/articles/fork-a-repo)
2. Add awesome code or fix an [issue](https://github.com/nickfloyd/newrelic-dotnet-agent-extensions/issues) with awesome code
3. [Submit a pull request](https://github.com/nickfloyd/newrelic-dotnet-agent-extensions/pulls)
