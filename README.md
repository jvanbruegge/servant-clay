# servant-clay - Servant support for Clay

Usage:
```hs
import Clay
import Servant
import Servant.CSS.Clay

import qualified Network.Wai.Handler.Warp as Warp

style :: Css
style = body ? background red

type API = Get '[CSS] Css

api :: Proxy API
api = Proxy

server :: Server API
server = return style

app :: Application
app = serve api server

main = Warp.run 3000 app
```
