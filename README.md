# Envelope-crypto

Library for envelope encryption and decryption implemented with NodeJS crypto package and Gcloud KMS service

#### Functions:
generate:
* Parameters: None
* Return: String
* Description: Generate a random 16-character string, intended to be used as plain datakeys.

encrypt:
* Parameters:
    + data: plain object to be encrypted
    + password: datakey to be used for data encryption
* Return: Encrypted object
* Description: Encrypt data using password and the AES-256-CTR algorithm

decrypt:
* Parameters:
    + data: encrpyted object to be decrypted
    + password: datakey to be used for data decryption
* Return: Decrypted object
* Description: Decrypt data using password and the AES-256-CTR algorithm

authGAPI:
* Parameters:
    + pri_key: Google service account private key that is authorized to use the Gcloud KMS service
* Return: None
* Description: Authenticate with Google Cloud Web API and store the access token on HTTP session if successful

kmsEncrypt:
* Parameters:
    + access_token: access token from Google Cloud authentication
    + password: datakey to be encrypted by Gcloud KMS
* Return: None
* Description: Key encryption done by Google services and store the response cipher on HTTP session if successful

kmsDecrypt:
* Parameters:
    + access_token: access token from Google Cloud authentication
    + ciphertext: cipher to be decrypted by Gcloud KMS
* Return: None
* Description: Key decryption done by Google services and store the response key on HTTP session if successful
