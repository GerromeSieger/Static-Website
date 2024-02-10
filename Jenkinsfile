pipeline {
  agent any
  triggers {
    githubPush()
  }
  stages {
    stage('Deploy') {
      agent any 
      steps {
        withCredentials([sshUserPrivateKey(credentialsId: 'remote-server-cred', keyFileVariable: 'SSH_PRIVATE_KEY', usernameVariable: 'REMOTE_USER')]) {
          script {
            sshCommand remote: [
              name: 'ec2server',
              host: '34.203.205.58',
              user: 'ubuntu',
              identiyFile: '-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAswNZnkQ6GgXkVFehhYMOHbdGdIq8gMR3RabWWcm5JTfo0md6
xgO3rciWC837yFzCkxwFLhhyjg7ZS4+jfcv3FJ/bRv9381MTVQ4HiV3/9GkOG9n4
SZU4hIT/YAy9WSB2MTpsTfcWWKHV/HGzGfOvk38p5mm7wT5iTKWsV9yS3omXFEC1
7nedFHBC/Wg4Z/AUfzCFqWCYFyKBMeOMJ5C58BgBtp09iza8V/sd3rVjjYQbuF7V
8+wntXhui/u9HQVePE9YC38REYdtLX1wnDKbMRVc1DdtxpKTnzM6sHDmsmIZ+tWQ
32L7Tw9c8kJLKVKrDB3Db77HUmflZmLnfp8HNwIDAQABAoIBAQCEpLnWFPX8bFs4
x8oOdQKTsEcLefWdcHZ0bOAtndSLqHbi2PxXF1AV/Ch6TMIBQAKJIN0Rv9m6O3R1
kdRyFR1a8ex4GjoWWXtcrc2V0soin2lt58AbPe+n+iiEUkxHa09IwOKZjrnHKPu3
V8R/OVri7vnsGnKeCQyrgKNIY0+Mhqfj5KjgIg4CP4HvHY1GrC6C2Dsf8jyNeEdw
2JHGaLpnlFNfe2yaT9sbVHz8vU0r8eVjOcy5d0AZ1ezJVpARhSLTMATPR523w7qI
S9eGFqxKX0h+mJAgseiMoZa0eGXb4bYBoC2BIwYlYWuekX5EXXIwAVD6NehPesPM
wr4gf+1ZAoGBANc3slCCirX/8dWgL9w5Zn/lxQgWxgAhFx2WVzWIU4shgfOQ5Q44
HSPool0L0EgIKjH6b1Pp3742/68yckV7mcegfp1PaQXDQJ5NflwAWeZgffigZ03e
BnZfrcg5anKKuItWLbO2lBjlsG+aQMiCZR0m+r8RbqCDOcQvtuUqfZLTAoGBANTv
W4ks7GauMYMIbAaxw5GD5DvxsCA97N8flBA9Sawqt1X8cA0tAQ2qnmgi7xe1SV+4
7oW9FN1siYIcsF7WU4AAdr8XxQXqgyAkyP0DTul+r9j+ItLVoH5RmOc9DoyipK5z
ctG1I3e5xag573dUQ3xVJHIfcszEKsvqE4O/gpONAoGAGza4voNzRMZDby7dPmyn
sF5+hqJSkSud/6jGCEffwIURKJpWzHB+Bs9g0IEw6hrWMxGmyCaXmzbbJ+0qE+0o
Kdz6havH7OmenyXPZ5THyWDELQ8jYO5FROyeTeYstqUh5sST7NiWa3uHzuTjcjdC
z+fg5w4uPe+5+zvJVbsEu+8CgYEAz+fJMz3GsFcChtMRTtQAhLMHhLPt6P0tq4mU
sup0ZYLrsSwiZ+r6LVLbCgiZ9EcQlkLluXUtyyivdnf2iRKxQrixONHHkIgycY8Z
I1k4kmkc3zz72Wm2I8AeECGgdBZVvvOAN1uqfrrHUAMJWjTPE7W6OSeVmnMq6iDp
3uh9YP0CgYAG8b9LKxvL6gxf97Bc9Kb+CAHFvle1ojdMgay3G28h+wYhDugxSZMA
+uTNs61Bi+1rGOLSjB0rnDVvxo4D+jGPFPP93Mte73x8EDUq263SPxZMWI69O70R
oY9ixU/gOHpAXMwUYY+RUrUYreLzLXlug2T/BmMVLdn/6NhzAhe4Kg==
-----END RSA PRIVATE KEY-----',
              allowAnyHosts: true
            ], command: "whoami"
          }
        }
    }
  }
}
}