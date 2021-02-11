# CryptoCode by JayMar921
 Version 1.0.0
   >Language:  Java
   >Requires Interface: None
   >Class Dependency:  None

   Note: This is made by educational purpose only, I am not responsible for any damage for your files
   
   Program Description: A program that encrypt/decrypt messages which requires arithmetic logic to encrypt the data using a  provided key and decrypt
   the message data depending on the special key that it requires for it to be unlocked. Incorrect unlock_key will result a broken decrypted data.
   
  largest possible key is 1,000,000,000,000,000 with encryption sequence of 243132002410432331 and unlock key of 2,000,000,000,000,000 or 2,000,000,000,000,001
   least possible key is 2 with encryption sequence of 14 and unlock key of 4 or 5


   To simplify
	Getting the  unlock_key will be the result of key*2;
   
   How to use 
      Create an object of CryptoCode
                                |
		               V
      CryptoCode <name> = new CryptoCode(key);

      Note: The key will be used to generate the encrypted data
            key input must be in range of (2 - 1000000000000000l) <- it is using the long datatype

      ::METHODS::

      .read("<filename>.extension")  <- reads the file and store its data in memory
                                                                     The data stored in memory will be the message_data(str)

      .write("data_", "<filename>")     <- writes the parameter data into a .dat file extension
      
      .encrypt()                                       <- it will encrypt the message_data using the key that
                                                                    was being used, note that the encrypted data will be stored
                                                                    in the memory,  it will be the encrypted_data(str)

      .decrypt(unlock_key)                  <- It reads the stored message_data(str) and decrypt the data however
                                                                   this requires a decryption key to decrypt its data,
                                                                   unlock_key range from  (4 - 2000000001)
                                                                   After the message was decrypted, it stores the decrypted_data(str)

      .encryptResult()               <- returns encrypted_data(str)
      .encryptShowKey()          <- returns encryption and decryption key
      .decryptResult()               <- returns decrypted_data(str)
      
   #DEMONSTRATION
      //creation  of  CryptoCode  object

      CryptoCode test = new CryptoCode(20);
      
      //ENCRYPTION OF DATA
      test.read("message.txt");                                             <- reads the file named "message.txt"
      
      test.encrypt();                                                                <- encrypts the contents of "message.txt"
      
      System.out.println(test.encryptShowKey());         <- Prints the encryption and decryption key (optional)
      
      test.write(test.encryptResult(), "test_result_encrypt"); <- stores the encrypted data into the "test_result_encrypt.dat"
      
      //DECRYPTION  OF DATA
      
      test.read("test_result_encrypt.dat");                        <- reads the file named "test_result_encrypt.dat"
      
      test.decrypt(40);                                                            <- decrypt the contents of "test_result.dat" using the unlock_key 40
      
      test.write(test.decryptResult(), "test_result_decrypt"); <- stores the decrypted data into the "test_result_decrypt.dat"



   Version 1.0.2
   >Language:  Java
   >Requires Interface: None
   >Class Dependency:  None

	NEW METHODS ADDED:

	.write("data_", "<filename>","extension") <- writes the parameter data into a custom file extension

	.encrypt("message")          			   <- it will encrypt the passed string data in it, it will not store the
                                        				   		encrypted data in the message_data(str) but it will return the 
                                      			   				encrypted data.

	.decrypt(unlock_key,"message") 		   <- It reads the passed string data and will use the decryption key
                                        						that is being provided. It will not store the decrypted data in
                                       							the memory but it will return the decrypted data.
