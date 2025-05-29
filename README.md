# Film-Searching
--- Nothing here! Please comeback later! ---
## get data and return to dataframe df
                  from pymongo import MongoClient
                  import pandas as pd
                  import ssl
                  
                  uri = "mongodb+srv://trandoanvuongtu:HB1j39319UxU2iHY@cluster0.2cudz7h.mongodb.net/?retryWrites=true&w=majority"
                  
                  # Kết nối client với tùy chọn SSL bỏ xác thực chứng chỉ
                  client = MongoClient(
                      uri,
                      tls=True,
                      tlsAllowInvalidCertificates=True
                  )
                  
                  # Truy cập vào database và collection
                  db = client["Film"]
                  collection = db["Data"]
                  
                  # Truy vấn dữ liệu
                  cursor = collection.find({}, {"_id": 0})  # Bỏ _id nếu không cần
                  
                  # Chuyển sang DataFrame
                  df = pd.DataFrame(list(cursor))
                  
                  print(df.head())
