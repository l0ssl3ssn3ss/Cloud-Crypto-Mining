# Cloud-Crypto-Mining
This repo was made for fun. Its contains a guide to mining SUGAR crypto via virtual cloud machines using Ansible.

NB:  You will need two or more cloud machines. You can set them up with this free $100 credit from [Linode](https://linode.com/seytonic)


1. First go on and create a SUGAR wallet [here](https://sugarchain.org/wallet/#/)

2. Open the terminal on one of your machines and run the following commands to setup Ansible:


   * `$ sudo apt update`

   * `$ sudo apt install software-properties-common`

   * `$ sudo add-apt-repository --yes --update ppa:ansible/ansible`

   * `$ sudo apt install ansible`

   * `$ cd /etc/ansible`

   * `$ ls`

   * `$ sudo nano hosts` 

>paste the following at the bottom of the host file:

>input all the ip addresses for your virtual machines:

```
[<name of your mining fleet>]
   
<IP address 1>
<IP address 2>
<IP address 3>
<IP address 4>
   
[<name of your mining fleet>:vars]

ansible_user=root
ansible_password=<same login password for root on all the machine>

#all the parameter <parameter> should be replaced
```


   * `$ sudo nano ansible.cfg`

>uncomment the following parameter:
   * `host_key_checking = False`


   * `$ sudo ansible minerig -m apt install sshpass`
  

3. Run the following command to edit the start-minerig.yml file to input run time and wallet address
  
   * `$ sudo nano start-minerig.yml`

4. Run the yml scripts using the ansible command:
  
   * `$ sudo ansible start-minerig.yml`
  
   * `$ sudo ansible setup-minerig.yml`
  
5. DONE, now go to the [pool.rplant](https://pool.rplant.xyz/) to monitor your your hashrate etc.


## Contributions

Please feel free to fork this repo, more crpto alternatives will be coming soon!

# References

[Mine Crypto On Google Cloud For Free](https://www.youtube.com/watch?v=XMGnWFrNL5U&list=LL&index=87&t=54s)

[NetworkChuck - you need to learn Ansible RIGHT NOW!! (Linux Automation)](https://www.youtube.com/watch?v=5hycyr-8EKs&t=746s)
