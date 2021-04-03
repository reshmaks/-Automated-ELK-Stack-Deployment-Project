# Create a Peer connection between the Virtual Networks.

This will allow traffic to pass between your vNets and regions. This peer connection will make both a connection from your first vNet to your Second vNet _And_ a reverse connection from your second vNet back to your first vNet. This will allow traffic to pass in both directions.

- Navigate to 'Virtual Network' in the Azure Portal.

- Select your new vNet to view it's details.

- Under 'Settings' on the left side, select 'Peerings'.

- Click the `+ Add` button to create a new Peering.

![](/Images/Peerings-side.png)

- Make sure your new Peering has the following settings:

- A unique name of the connection from your new vNet to your old vNet.
- Elk-to-Red would make sense

- Choose your original RedTeam vNet in the dropdown labeled 'Virtual Network'. This is the network you are connecting to your new vNet and you should only have one option.

- Name the resulting connection from your RedTeam Vnet to your Elk vNet.
- Red-to-Elk would make sense

- Leave all other settings at their defaults.

![](/Images/vNet-images/Peering.png)

![](/Images/vNet-images/Peerings-final.png)


