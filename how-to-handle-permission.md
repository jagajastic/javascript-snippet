### How to handle user permission 

This is for simple role based system
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

Note: for complex kind of role base system use this formula: attribute:resource(s):action

attribute: it can be a user, admin,organization,channel etc
resource(s): it can be a file, folder, a user, an action or attribute it self.
action: delete, create, view, update etc.
