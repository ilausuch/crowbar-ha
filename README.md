Description
===========
This is a cookbook for installing and configuring pacemaker.

Recipes
=======
default
-------
Installs and start `pacemaker`. 

config
-------
Configures pacemaker resources such as primitive, location, colocation and order.

Resources/Providers
===================
There are 7 LWRPs for interacting with pacemaker.

primitive
----------
Configure and delete primitive resource. 

- `:create` configures a `primitive`
- `:delete` deletes a `primitive`

### Examples
``` ruby
pacemaker_primitive drbd do
  agent "ocf:linbit:drbd"
  params {'drbd_resource' => 'r0'}
  op {'monitor' => { 'interval' => '5s', 'role' => 'Master' } }
  action :create
end
```

License and Author
==================

Author:: Robert Choi <taeilchoi1@gmail.com>

Copyright:: 2013 Robert Choi

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
