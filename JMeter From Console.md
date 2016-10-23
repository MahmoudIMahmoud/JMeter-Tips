#How to run JMeter in Non GUI mode
1.  Open command prompt
2.  Go into JMeter’s bin folder
3.  Enter following command,
```shell
  jmeter -n –t <your plan.jmex> -l <jmeter output file>.jtl
```
______
Where:
______
|Parameter|Means|
|---|----------------|
| n | non gui |
| t | test plan file |
| l | output log |


###How to view the results?
>1.  Open JMeter in GUI mode.
2.  Add any listener Eg. View Results Tree/**summary Report.**
3.  Click Browse button of the file name field in listener.
4.  Open testresult.jtl file.

###You should be able to see the result in listener now.

![Alt](/JMeterLoadResults.png "Results")
