# k8stcpdump a tool to collect tcpdumps from the nodes.
to install :
- Create a storage account to hold the capture in your MC_rg 
- update your helm repo by : helm repo add k8tcp https://digeler.github.io/k8stcpdump/
- install the chart by : helm install k8tcp/kubecapture --set sa=[name of the stroage account]
you should see the captures in the share.
-to stop the capture just remove the chart helm delete [chart name]

####Notice : Please change the Reclaim policy of the pv to Retain instead of Delete.
kubectl edit pv 
this will keep the traces after you stop the trace.
