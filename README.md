# Film-Searching
--- Nothing here! Please comeback later! ---
## Get data and return to Data frame df
---step 1--pip install pymongo---
                  from pymongo import MongoClient
                  import pandas as pd
                  import ssl
                  
                  uri = "mongodb+srv://trandoanvuongtu:HB1j39319UxU2iHY@cluster0.2cudz7h.mongodb.net/?retryWrites=true&w=majority"
                  client = MongoClient(
                      uri,
                      tls=True,
                      tlsAllowInvalidCertificates=True
                  )
                  db = client["Film"]
                  collection = db["Data"]
                  cursor = collection.find({}, {"_id": 0}) 
                  df = pd.DataFrame(list(cursor))
--------------------
