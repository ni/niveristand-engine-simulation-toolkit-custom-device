#!/usr/bin/env groovy
//Leave the above line alone.  It identifies this as a groovy script.
@Library('vs-build-tools') _

def lvVersions = ['2018']

ni.vsbuild.PipelineExecutor.execute(this, lvVersions)
diffPipeline('2018')
