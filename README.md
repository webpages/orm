ORM for WebPages
===

**ORM** (Object-relational mapping) - is a toolset to access database (DB).

This ORM can be used independently, but originally designed to use with [WebPages python web framework](https://github.com/webpages/webpages).


News
---

 * In **Dec 2014** [PostgreSQL 9.4](http://www.postgresql.org/about/news/1557/) brings JSON field type support. We like this and will use this feature in our ORM


Syntax overview
---

```python
>>> User.first
# return first found object, ordered by default field
>>> User.first(10)
# return first 10 users
>>> User.first('-date', 'name')
# custom order
>>> User.first(10, '-date', 'name')
# custom order for multiple objects
>>> User.last
# the same as User.first but in inversed order
>>> User.all
# return all objects, ordered by default field
>>> User.find()
# find objects by criteria
>>> User.find(
>>>     F.name='Tony' and
>>>     (F.age>18 and F.age<35) and
>>>     (F.is_admin=True or F.role.name.in('admin', 'manager'))
>>> )
```
