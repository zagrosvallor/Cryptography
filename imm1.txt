def machine():
    keys = 'abcdefghijklmnopqrstuvwxyz !'

    values = keys[-1] + keys[0:-1]

    encryptDict = dict(zip(keys, values))
    decryptDict = dict(zip(values, keys))

    message = input('please enter your secret message')
    mode = input("crypto mode: Encode(E) or Decode(D)")

    if mode.upper() == 'E':
        newMessage = ''.join([encryptDict[letter]
                              for letter in message.lower()])
    elif mode.upper() == 'D':
        newMessage = ''.join([decryptDict[letter]
                              for letter in message.lower()])
    else:
        print("Please try again, wrong choice entered")

    return newMessage.capitalize()

print(machine())


