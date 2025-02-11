### How to handle user permission 

<code>

type Role = typeof typeof PERMISSION
type Permission = (typeof PERMISSION)[Role][number]

  const PERMISSION = {
    admin: [
    'view:comment',
    'create:comment',
    'delete:comment',
    'update:comment'
    ],
    moderator: [
      'view:comment',
      'create:comment',
      'delete:comment',
      ],
    user: [
      'view:comment',
      'create:comment',
      ]
  } as const


  function hasPermission(user, role: Permission){
    return (PERMISSION[user.role] as readonly Permission[]).includes(role)
    
  }
</code>
