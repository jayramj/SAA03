* Data Origina Authentication - Is the data really from the source you think it is
* Data Integrity Protection - Data hasn't been modified in transit
* DNSSec doesn't correct anything. It only validates if something is genuinely from a source or not or it has been altered or not.
* KMS creates a KSK i.e. Key Signing Key.In Route53 , AWS creates ZSK i.e. Zone Signing Key
* R53 KSK & ZSK public parts into  DNS Key Record.
