# sample code #

```
RadiusClient rc = new RadiusClient(hostname,sharesecret);
RadiusPacket authPacket = rc.Authenticate(login,password);
if(authPacket == null) throw new Exception ("Can't contact remote radius server !");
switch (authPacket.Type) {
	case RadiusPacketType.ACCESS_ACCEPT :
    	Console.WriteLine("accepted");
        foreach (RadiusAttribute attr in authPacket.Attributes) {
        	Console.WriteLine(attr.Type.ToString()+ " = " + attr.Value);
        }
        break;
    default :
      	Console.WriteLine("rejected");
        break;
    }
}
```