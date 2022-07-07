This project is aimed at providing a series of handy packages for the development of a classic CRUD web application.  
The packages are work around a standard database table definition schema writter in JSON.   
An example is provided below and the full definition can found here: [TableDefinition](https://github.com/easycrud/toolkits/blob/master/index.d.ts#L86)

```
{
  tableName: 'users',
  columns: [
    {
      'name': 'id',
      'type': 'int',
      'length': 11,
      'primary': true,
      'autoIncrement': true,
    },
    {
      'name': 'username',
      'type': 'varchar',
      'length': 256,
      'default': '',
      'comment': '用户名',
    },
    {
      'name': 'email',
      'type': 'varchar',
      'length': 512,
      'comment': '邮箱',
    },
    {
      'name': 'password',
      'type': 'varchar',
      'length': 512,
      'comment': '密码',
    },
    {
      'name': 'update_time',
      'type': 'timestamp',
      'default': 'CURRENT_TIMESTAMP',
      'onUpdate': 'CURRENT_TIMESTAMP',
      'comment': '更新时间',
    },
  ],
  indexes: {
    idx_user: {
      columns: ['username', 'email'],
      unique: true,
    },
    idx_email: {
      column: 'email',
    },
  },
}
```