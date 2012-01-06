## Key Structure

The leftmost (decimal) digit is a Verhoeff check digit to identify transmission errors, particularly human transcription errors.

The remaining digits are a combination of the table key and the row key. The least-significant 8-bit bytes represent the table key; the least significant 7 bits of each byte is the table key, and the most significant bit indicates if the current byte is the last byte of the table key. When this indicator bit is 1 (2^7), the current byte is the last byte of the table key, and the remainder of the number is the row key.

## Supporting Functions

Key ( rowKey ; tableKey )	// creates the key
KeyGetTable ( theKey )	// returns the original tableKey
KeyGetRow ( theKey )	// returns the original rowKey
KeyIsValid ( theKey )	// verifies the check digit