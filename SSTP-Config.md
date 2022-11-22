# SSTP

### *Step1:* Config Pool IP
<br/>

>- Add your Considered Range of IP on This Location (IP---->Profile)
>
>
<br/>

### *Step1:* Config Profile
<br/>


>- Profile Location on Mikrotik (PPP---->Profile)
>
>- First Step set Local Address with Range of your Pool IP
>
>- Second Step set Dns Server with Range of your Pool IP
>
>- Third Step set Remote Address whith your pool IP Name's
>
<br/>

### *Step3:* Config Secret (Users Account)
<br/>

>- Secret Location on Mikrotik (PPP---->Secret)
>
>- First Step set Name And Password for your Users
>
>- Second Step set Specified Service for your Users
>> Example:you can set SSTP for one user and set L2tp for another user or you can set Any for users that they can Connect to your Server with All Avilable Protocol
>

<br/>

### *Step4:* Create Certificate 
<br/>

    you should create Certificate whit two subject :

      Certificate Location on Mikrotik (System---->Certificate)

         CA Certificate:

             First Step set Name (CA)
             Second Step set 5 Next Field with your desired Name
             Third Step set Common Name and Subject Alt.Name with your Server IP's
             fourth Step in Key Usage Check Key cert.sign and crl sign
             fifth Step sign this Certificate 

         Server Certificate:
            
             First Step set Name (Server)
             Second Step set 5 Next Field with your desired Name
             Third Step set Common Name and Subject Alt.Name with your Server IP's
             fourth Step in Key Usage Check Key digital signiture
             and key encipherment and tls server
             fifth Step sign this Certificate with exist CA
             ** After sign this Certificate you should Check trust field **
     


### *Step5:* Enable SSTP Server

<br/>


>- SSTP Server Location on Mikrotik (PPP---->Interface---->SSTP Server)
>
>- First Step check Enable field
>
>- Second Step check mschap2 field
>
>- Third Step set Server for Certificate 
>
>- fourth Step set on Default Profile with Created Profile
>
>- **you can Change your port**
<br/>


### *Step6:* Config Nat

<br/>

>- Nat Location on Mikrotik (IP---->Firewall---->Nat)
>
>- First Step set chain (srcnat)
>
>- Second Step set Action (masquerade)
>

