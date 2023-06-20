# mugshot
This will upload a screenshot of your own ped (face/mugshot) and return the image url. This is a client-sided function.

### Installation
1. Install my modified <a href="https://github.com/jonassvensson4/screenshot-basic">screenshot-basic</a> resource.
2. Add `start mugshot`to your server.cfg. <br>Remember to start it after screenshot-basic and before your scripts that are using the export.
3. This resource uploads images to imgur, you'll need to create a client and add your client ID to the top of the client.js. You can create a client here: https://api.imgur.com/oauth2/addclient


#### JavaScript example
```javascript
exports['mugshot'].getMugshotUrl(PlayerPedId(), ( url ) => {
    emit('chat:addMessage', {
        template: '<img src="{0}" style="width: 160px; height: 170px;" />',
        args: [url]
    });
});
```
#### LUA example
```lua
exports['mugshot']:getMugshotUrl(PlayerPedId(), function ( url )
    TriggerEvent('chat:addMessage', {
        template = '<img src="{0}" style="width: 160px; height: 170px;" />',
        args = {url}
    })
end)
```# mugshot
