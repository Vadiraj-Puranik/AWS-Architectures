# AWS Security 

Here we come across mainly 2 Points listed below :<br>
* Encryption 
* Certificates 



## Encryption:

Symmetric encryption :<br>
Only one key is used to both encrypt and decrypt the data.<br>
If the key is compromised then data is compromised <br>
Example: Alice uses a key and encrypts the data and sends the data and key to bob . If the key is compromised during the transit then the data is compromised.<br>
![Symmetric-Encryption-Image-extracted-from-57](https://user-images.githubusercontent.com/113619300/209456029-bffb3a72-79c0-4424-b469-d23d93595bdf.png)

Asymmetric encryption:<br>
Public and private keys are used for eccryption and decryption of the data respectively.<br>
Public key is readliy available and anyone can access from the web.<br>
Example : Alice uses Bobs public key and encrypts the data . Bob uses the private key with respective to the public key he sent to Alice earlier and decrypts the data.
Data cannot be compromised since it is associated with only public key of bob.<br>
Issue: How is alice confirming if the public key sent to her is of Bob's? Anyone can compromise and replace bobs key with their public key . 
Solution : Here comes certification authority who signs the certicate and confirms that its the bob's key .
![download](https://user-images.githubusercontent.com/113619300/209456145-9106a94d-866e-47d3-8b33-88ad2ad6e8b7.png)



## Certificates:

Certifcates are signed by the Authorites and provides that the key sent is of respective owner .<br>
How does this work?<br>

Step 1:Bob reaches out to certificate authority with his public key and requests them to sign it.<br>

Step 2: Certificate authority issues the certificate for the public key and adds signature as a proof that its Bobs .<br>
Proof: Certificate authority uses its private key and encrypts(sign) at the end of certificate<br>

Step 3: Alice asks for communication and now Bob sends the certificate first<br>

Step 4: Alice takes the certificate(Certificate has bobs Public key and signature of Certificate Authority)<br>

Step 5: Alice uses certificat Authority's Public key and decrypts the signature . After decryption the data (Signature) will match the Bobs public key and hence confirms<br>
Its bobs public key.<br>
Its important to note here is that Certification Authority encrypts Bobs certificate with its PRIVATE KEY . And Alice will get Certification Authority's Public key when Alice makes request for Bob to connect.



Alice -> Request for communication-> Bob <br>
Bob sends Certificate with Root Level to Alice <br>
Alice Decrypts signature and matches bobs public key to check if its legit via public key of Certification Authority sent by Bob<br>
Once verified Alice uses Bobs public key and encrypts the data . Bob uses his private key to decrypt the data and now its secure.

![image](https://user-images.githubusercontent.com/113619300/209456415-f9a29630-3f5f-47f4-b880-14ce257a14f9.png)



### Role of AWS 

Encryption : AWS KMS helps in encryption process(Its managed by AWS)<br>
Certificate: AWS Certificate Manager Provides support for Certication.


