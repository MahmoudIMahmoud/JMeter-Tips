pipeline {
   agent any
   stages {
      stage('Run') {
         steps {
            echo '%JMeterHome%'
            echo 'Running ...'
            bat label: '', script: '%JMETER_HOME%\\bin\\jmeter.bat -n -Jjmeter.save.saveservice.output_format=xml -t ./TestPlanx.jmx -l outputx.jtl'
         }
      }
     stage('Reporting ...') {
         steps {
            echo 'Report'
            perfReport excludeResponseTime: true, filterRegex: 'Label0|Label01', sourceDataFiles: 'outputx.jtl'
         }
      }
   }
}
