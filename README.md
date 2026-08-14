# My Jellyfin 
Docs and instructions on accessing my jellyfin server. Follow the steps below to get access to my media library :>

Skip to [Prerequisites](#Prerequisites) for how to get setup.

## Tech Stack

All the products used are FOSS (free and open source) and I would encourage everyone to check them out.

#### Jellyfin #####

[Jellyfin](https://jellyfin.org/) is the media server I use to stream content from my media library. This includes movies, tv shows, and music. The server is running from my house, meaning it can only be accessed from my home network by default.

Docs: https://jellyfin.org/docs/

#### Tailscale

[Tailscale](https://tailscale.com/) is a VPN provider that I am using to enable access to my jellyfin server outside my house. This is how I am able to share my jellyfin instance with other people as well. I have a tailscale account that defines my "tailnet". A [tailnet](https://tailscale.com/docs/concepts/tailnet) is basically my personal VPN network, which jellyfin is broadcast on. So by connecting other devices to my tailnet, they are able to discover and use the jellyfin server. I am able to add users to my tailnet which gives them access as well. 

I am using Github as my identity provider for my tailnet, meaning users will create a tailnet account via Github. I am also using a Github org for managing access to my tailnet, meaning I will have to add users to my Github org.

Right now I am using the free plan which allows for up to 6 users on a tailnet. I may upgrade to a standard account at some point to allow for unlimited users, but tbd.

Docs: https://tailscale.com/docs

## Prerequisites

1. You must have a Github account. Create one here if you don't have one or if you want a new one for this: https://github.com/signup. [^1]

	You **MUST** have 2FA enabled and a verified email address on your account.
	
	You will be added to my Github org in order to access my tailnet, so if this is something you want to isolate from your main account then I would reccomend creating a new one. Especially if you don't have 2FA enabled and don't want to enable it on your main. 

	Get help with creating an account [here](https://docs.github.com/en/account-and-profile/how-tos/account-management/creating-an-account-on-github) if needed. 

1. Install tailscale client on your device: https://tailscale.com/download

    It's available on ios, android, windows, macOS, linux. It is not available on most smart TVs so to watch on your TV connect on your phone/computer, and stream to TV via cast or hdmi etc. You **MUST** have tailscale on the client you wish to access jellyfin from.

1. (Optional) Install jellyfin client on your device: https://jellyfin.org/downloads/clients/
    
    This is technically optional, as you can stream from jellyfin in your browser if you want. I would reccomend the official client, as it contains settings that are nice to have for streaming.

## How to connect

Copying [these instructions](https://tailscale.com/docs/integrations/identity/github#join-a-github-organization-tailnet) for how to join my tailnet:
1. First I have to add you to my Github org: "`batdan-tailnet`". Send me your Github username or email address. I will send you an invite which you will recieve via email. Accept the invite via email or visit https://github.com/batdan-tailnet to accept. 
1. Go to https://login.tailscale.com/login, select "`Sign in with Github`". This will redirect you to log in to Github.
1. Be sure "`Organization access`" to "`batdan-tailnet`" is granted. You will see a green check mark next to org name if so. Then select "`Authorize tailscale`".  You will then be redirected to "`Select a tailnet`" page.
1. Select the tailnet to join, in this case you will select:   
	```  
	batdan-tailnet.org.github
	```
1. You should see a confirmation message and a link to download tailnet on your device (which you should follow if you haven't downloaded on your desired device yet).
1. I will have to approve you membership to my tailnet, so let me know once you reach the previous step and I will approve your account.
1. Once approved, log in to your tailnet account on the device you want to stream jellyfin on. 

Next you simply have to connect to my jellyfin server:
1. I will start by making a jellyfin account for you, so let me know what you want your username to be. I'll then send you login creds.
1. Open the jellyfin app and you should be prompted with a server URL. Enter the following:
    
    ```
	https://jellyfin.wyrm-shiner.ts.net/
    ```
1. If connection is successful, you will be prompted with a login. This is a login to jellyfin itself, not tailnet. Use the login info I sent here. I would encourage you to change the default password I provisioned for you.
1. Once logged in, you should be good to go. Browse around and let me know whatever issues come up!


## Further Reading

If you want random thoughts/info on my setup, see here: [docs](./docs)



### Footnotes

[^1]: It's worth noting that tailnet restricts joining more than 1 external tailnet at a time by default: [enable-or-disable-joining-external-tailnets](https://tailscale.com/docs/features/sharing/how-to/invite-any-user#enable-or-disable-joining-external-tailnets). I do not plan on changing this for my tailnet, so if that is something to consider when using existing github account or making a new one. If you have other external tailnets you want your main github account to join, you should make a new account. IIUC this does not prevent you from creating your own tailnet on an account, just from joining others.

