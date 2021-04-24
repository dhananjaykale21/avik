# avik

def otp_generator(email):
    length=len(email)
    otp=0
    if length>12:
        otp=otp+10
    if email.endswith((".org",".in")):
        otp=otp+11
    if email[5] in (".", "_"):
        otp=otp+12
    if email[0:2].lower()==email[length-2:length].lower():
        otp=otp+13
    for index in range(0,length):
        if email[index].isdigit():
            otp=otp+index
    if otp==0:
        otp=-1
    return otp
    
email="USgana@a.us"
otp=otp_generator(email)
print(otp)


