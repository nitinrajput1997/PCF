# PCF

Policy are simply a rule for how the 5G system can manage the different users, data sessionscor different data flows. The policy themselves can be specified as different level of granularity such as

i) there are policies that affect all the users in the same manner
ii) second there are some policies that are user specific, but it affects all the services of the user in the same manner
iii) third there are video session or IP data flow specific policies, which affect net only those applications or data flows

Now PCF is not working independently. To make best policy level decision, it works together with a lot of other network functions.

There are two kind of policies 

i) session related schlender policies: The policy that are related to PDU session is known as session related policies. Example the policies about what application traffic is supported in PDU session and what is forbidden forbidden usually handled by session related policies and also what application get higher or lower priority is also comes under this policy.

Second non session related policy when the policy are related to user specific are known as non session related policy. Example if some users are allowed to access the 5G system in a certain geography and not in some other area, that geographical description is a policy that is under non session related policy.


Non-Session Related Policies

i) Access and Mobility Related Policy
   
   - Service Area Restriction
	if a device or a user is allowed to access 5G system in certain geographical areas and not in others it is allowed to access certain kind of service in some low graphical areas and not others. This is called as service area restriction.

   - RAT/frequency selection priority 
	when a device is accessing a 5G system, it can be seen that the 5G is available over multiple frequency bands in such situation, the device need a guidance on which is the highest priority frequency to access. This way, the operator choosing the frequency that is expected to provide the best performance will be, what the device will choose as preferred frequency.

ii) Policies to the UE
    
    - UE Route Selection Policy
	suppose a device is connected to a 5G system and has ongoing PDU session. Now, if a user opens his new application say YouTube and want to stream videos. Now the device has to decide, if existing PDU session can be used for YouTube or if it should create a new PDU session. To help the decision like this, we have UE Route Selection Policy.

    - Access Network Discovery and Selection Policy
	in some scenario, Wi-Fi network is used to support 5G connectivity where the 5G coverage is sometimes poor. Suppose there might be a case where the devices sees multiple Wi-Fi network available. Then there should be some sense of priority in locating the Wi-Fi network and choose the right access network. This policy will help to choose the right Wi-Fi network in a given situation.

iii) Packet Flow Description
     it refers to the set of information which helps the network to detect the application traffic. We have seen that in QoS, a multiple application related traffic can be carried from data network to gNodeB. But not all the application has to be treated the same way. Example if operator has an agreement that if you stream music through specific music stream service then they don't charge you for it that means they won't charge the data it consumes. Then we need a policy that will make the UPF, not to measure the amount of data concerning that particular application. So we need packet flow descriptor, that will help the UPF to understand what kind of characteristic will describe a particular application.

iv) Session Management Related Policies

    - Gating Control
	vanna this type of policies are used to block or aloda IP packets office certain service listov. Example in some countries torrent or block so all the IP packets that corresponding to P2P targeting are system is blocked.

    - Quality of Service Control
	There might a case where not all the application are allowed to be treated in the same manner. Some have higher priorities and some have lower priorities. This is defined by the QoS control, where the QoS policies define the quality of particular authorized service should get.

**Policy Flows**

Whenever the PCF make decisions, it usually cold PCC rules or policy and charging control rule. But this rule cannot send directly into the network. So the PCC rule are send by the PCF to SMF and SMF uses it to enforce different kind of behavior across the network. It takes the PCC rules and identifies what should be the SDF or service dataflow template that SMF should send to you UPF. What does upf need don't know. It need to know how it can differentiate with the different service running on the network example it needs to differentiate between the IP packet from applications like Spotify, ah IP packet from You Tube, IP packet from Internet browsing. On the other hand gNB, needs to know quality of service profile which helps gNB to put the different quality of service flow in the right radio bearers in the wireless network. When the traffic is available, the UE need the guidance on what uplink barrier to use to send the different application traffic so this one governs by the quality of service rules.

