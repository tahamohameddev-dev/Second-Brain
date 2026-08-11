# All import for api
```python
from fastapi import FastAPI, Response, status, HTTPException, Depends
from pydantic import BaseModel
from typing import Optional
from random import randrange
import psycopg2
from psycopg2.extras import RealDictCursor 
import time
from . import models
from .database import engine, get_db
from passlib.Context import CryptContext
```

# Database for Api

## import
```python
import psycopg2

from psycopg2.extras import RealDictCursor
```

## Code

```python
while True:
    try:
        coon = psycopg2.connect(host='localhost', user='postgres', password='taha116741', curcor_factory=RealDictCursor)
        print("Database connection was successfully!")
        break
    except Exception as error:
        print("connecting to database failed")
        print("Error: ", error)
        time.sleep(3)
```

## تحديث الكود والاتصال بقاعدة البيانات ب الطريقه الجديده 

```python
# thes is file database.py
from sqlalchemy import create_engine
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

SQLALCHEMY_DATABASE_URL = 'postgresql://postgres:password123@localhost/fastapi'

engine = create_engine(SQLALCHEMY_DATABASE_URL)

SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)

Base = declarative_base()
```

## create data base in python dont need sql 

```python
from sqlalchemy import Column, Integer, String, Boolean
from sqlalchemy.sql.exception from null
from .database import Base

class Post(Base):
    __tablename__ = "post"
    
    id = Column(Integer, primary_key=True, nullable=False)
    title = Column(String, nullable=False)
    content = Column(String, nullable=False)
    published = Column(Boolean, server_default='TRUE')
    created_at = Column(TIMESTAMP(timezone=True), server_default=text('now()'))
```

## line for run database in file main

```python
models.Base.metadata.create_all(bind=engine)
```

## hash password
```python
pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
# pwd_context = كائن مسؤول عن تشفير/فحص الباسوردات
# schemes=["bcrypt"] = نوع خوارزمية التشفير المستخدمة
# deprecated="auto" = لو فيه خوارزميات قديمة تانية، تتعامل معاها أوتوماتيك


@app.post("/users")
def create_user(user: schemas.UserCreate, db: Session = Depends(get_db)):
    """
    بيستقبل بيانات يوزر جديد (email + password)،
    يحول الباسورد لـ hash قبل ما يخزنه في الداتابيز،
    عشان الباسورد الأصلي متتخزنش أبداً في أي مكان.
    """
    hashed_password = pwd_context.hash(user.password)
    user.password = hashed_password  # نحدث الكائن نفسه بالـ hash بدل الباسورد الأصلي
    ...
```