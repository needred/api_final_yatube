# API Yatube
### ��������
API ��� ������� Yatube - ������ � �������, ��������, ������������� � ����������.

### ��� ��������� ������:

����������� ����������� � ������� � ���� � ��������� ������:

```
git clone https://github.com/needred/api_final_yatube
```

```
cd yatube_api
```

C������ � ������������ ����������� ���������:

```
python -m venv env
```

```
. venv/Scripts/activate
���
. venv/bin/activate
```

```
python -m pip install --upgrade pip
```

���������� ����������� �� ����� requirements.txt:

```
pip install -r requirements.txt
```

��������� ��������:

```
python3 manage.py migrate
```

��������� ������:

```
python manage.py runserver
```

### ������� �������� � API:

�������� **������ ���� ����������**:

```
GET http://127.0.0.1:8000/api/v1/posts/
GET http://127.0.0.1:8000/api/v1/posts/?limit=2&offset=4
```

���������� **����� ����������** � ��������� ����������:

```
POST http://127.0.0.1:8000/api/v1/posts/
{
    "text": "����� �����",
    "image": "string",
    "group": 0
}
```

��������� **���������� ����������** �� id. �������� ���������� ����� ������ ����� ����������:

```
PATCH http://127.0.0.1:8000/api/v1/posts/2/
{
    "text": "������������ ����� �����"
}
```

��������� **���� ������������** � ����������:

```
GET http://127.0.0.1:8000/api/v1/posts/4/comments/
```
_��� 4 - id ���������� (post_id)_

��������� **�����������** � ���������� �� id:

```
GET http://127.0.0.1:8000/api/v1/posts/4/comments/1/
```

��������� ���������� � **����������** �� id:

```
GET http://127.0.0.1:8000/api/v1/groups/3/
```

**�������� ������������** �� ����� �������� ������ ������ �� ������������ ����������� � ���� �������:

```
POST http://127.0.0.1:8000/api/v1/follow/
{
    "following": "user234"
}
```

��������� **JWT-������**:

```
POST http://127.0.0.1:8000/api/v1/jwt/create/
{
    "username": "user234",
    "password": "DLkt48NbvmC"
}
```
