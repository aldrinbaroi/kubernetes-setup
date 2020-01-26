# kubernetes-setup-centos7
Script to setup Kubernetes cluster using CALICO POD network on CentOS 7 


        kubernetes-setup usage:
         
          kubernetes-setup -b | -j | -s SETUP_OPTIONS | -h
         
            -b     Get Kubenetes dashboard URL & login token
            -j     Get slave node's cluster join command
            -s|-r  Setup/reinstall kubernetes node (master|slave)
            -h     Show this usage text
         
            SETUP_OPTIONS: -t node-type [-n node-name] [-i node-iface -a node-ip] [-u node-user] [-d log-dir]
         
              -t node-type    Kubernetes node type [master|slave]
              -n node-name    Kubernetes node's host name
              -i node-iface   Kubernetes node's network interface name
              -a node-ip      IP address & netmask  Ex:  172.16.0.2/255.255.0.0
              -u node-user    Kubernetes admin user other than 'root' for running kubectl
              -c              Setup dashboard. Only applies to master node. By default dashboard is not setup
              -d log-dir      Overrides default log directory 
         

        kubernetes-setup config file: kubernetes-setup.conf
         
          Change the following to match your setup:

          KMASTER_IP_ADDRESS  Master node's IP address
          KMASTER_NODE        Master node's IP address, hostname, short hostname
          KSLAVE_NODES        List of slave nodes' IP address, hostname, short hostname
          KADMIN_USER         Admin user's login ID
          KADMIN_PASSWORD     Admin user's login password

          Notes: 
          1) Values for KMASTER_NODE & KSLAVE_NODES must be in valid JSON format.
          2) Admin user will be created if the user doesn't exists.
          3) Before running slave node setup, copy the "kslave-cluster-join-command" file from the master node.
 
