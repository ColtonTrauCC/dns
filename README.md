<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1 align = "center">Understanding and Building Intuition for DNS (Domain Name System)</h1>
This lab demonstrates the use of DNS and how to configure it. DNS serves as the phonebook of the Internet, translating domain names to IP addresses so browsers can load Internet resources (essentially why we don't need to type IP addresses to access Google.com). To see how it works in practice, this lab follows up from the <a href = "https://github.com/ColtonTrauCC/active-directory">installation and configuration of an Active Directory</a>. When configured and installed, we'll perform excercises with the client and domain controller virtual machines in order to understand DNS a bit better.

<br />

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Active Directory Domain Services</li>
  <li>Command Prompt</li>
</ul>

<br />

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 Pro (21H2)</li>
</ul>

<br />

<h2>DNS Exercises</h2>

<!-- <img src = "" width = 80% height = 80% /> -->

<h3>A-Record</h3>

<p>
  <ul>
    <li>The "A" in A-Record stands for "address" and this is the most fundamental type of DNS record: pointing to the name of the IP address of a given domain.</li>
    <li>Connect and log in to your Domain Controller and Client virtual machines as admins <b>(mydomain.com\jane_admin)</b></li>
    <li>In the Client VM, open up Command Prompt and attempt to ping "mainframe" by entering the command <b>ping mainframe</b>; you will notice it will fail</li>
    <ul>
      <li><img src = "https://github.com/ColtonTrauCC/dns/assets/147654000/cef4c81c-bc99-4dcf-a546-10ecdd6935a9" width = 80% height = 80% /></li>
    </ul>
    <li>The same result also applies if we attempt and nslookup of the mainframe (command line <b>nslookup mainframe</b>) because we do not have a DNS record</li>
    <li>To create a DNS A-Record, go to the Domain Controller VM and open the <b>DNS Manager</b>b> in the Server Manager Board and go to the domain you created within the <b>Forward Lookup Zones</b> tab (mydomain.com)</li>
    <li>Right click on the page and create a <b>New Host</b>. We will name the host <b>mainframe</b>b> and the IP address should be the same IP as the domain controller so that ping can resolve. Once the information is entered, click <b>Add Host</b> and refresh the DNS server so that the new record can be updated.</li>
    <ul>
      <li><img src = "https://github.com/ColtonTrauCC/dns/assets/147654000/ee7f533c-ae4d-4484-9854-9790a3766b20" width = 80% height = 80% /></li>
    </ul>
    <li>Head back to the Client VM and attempt to ping the mainframe again, the issue should be resolved and receive the ping successfully</li>
    <ul>
      <li><img src = "https://github.com/ColtonTrauCC/dns/assets/147654000/5f27f8a2-fc9f-4379-9f0d-b53a2b4312b3" width = 80% height = 80% /></li>
    </ul>
  </ul>
</p>

<br />

<h3>Local DNS Cache</h3>

<p>
  <ul>
    <li></li>
  </ul>
</p>

<br />

<h3>CNAME Record</h3>

<p>
  <ul>
    <li>"CNAME" is abbreviated form of "Canonical Name:" pointing to a name to another name instead of to an IP address unlike A-Record</li>
  </ul>
</p>

<br />
