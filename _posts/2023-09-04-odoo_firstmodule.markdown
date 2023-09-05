---
layout: post
title:  "Creating an Odoo module"
date:   2023-09-04 07:30:30 +0200
categories: odoo erp frontend
---

Below is a simple example for creating a new Odoo module. This is a basic "To-Do" list module. The module has just one model `Todo.Task` with a name and a description.

1. Create a new directory named `todo_app` in your Odoo addons folder.

2. Inside `todo_app`, create two files:

    - `__init__.py`
    - `__manifest__.py`

3. Create a folder named `models` and another one named `views`.

4. Inside `models`, create a Python file named `todo_model.py`.

5. Inside `views`, create an XML file named `todo_view.xml`.

### `__init__.py`
```python
from . import models
```

### `__manifest__.py`
```python
{
    'name': 'To-Do App',
    'description': 'Manage your personal To-Do tasks.',
    'author': 'Your Name',
    'depends': ['base'],
    'application': True,
    'data': ['views/todo_view.xml'],
}
```

### `models/todo_model.py`
```python
from odoo import models, fields

class TodoTask(models.Model):
    _name = 'todo.task'
    _description = 'To-Do Task'

    name = fields.Char('Name', required=True)
    description = fields.Text('Description')
```

### `views/todo_view.xml`
```xml
<odoo>
    <record id="view_todo_task_form" model="ir.ui.view">
        <field name="name">todo.task.form</field>
        <field name="model">todo.task</field>
        <field name="arch" type="xml">
            <form>
                <group>
                    <field name="name"/>
                    <field name="description"/>
                </group>
            </form>
        </field>
    </record>

    <record id="view_todo_task_tree" model="ir.ui.view">
        <field name="name">todo.task.tree</field>
        <field name="model">todo.task</field>
        <field name="arch" type="xml">
            <tree>
                <field name="name"/>
            </tree>
        </field>
    </record>

    <record id="action_todo_task" model="ir.actions.act_window">
        <field name="name">Tasks</field>
        <field name="res_model">todo.task</field>
        <field name="view_mode">tree,form</field>
    </record>

    <menuitem id="menu_todo_task" name="To-Do Tasks" parent="base.menu_custom" sequence="10" action="action_todo_task"/>
</odoo>
```

Finally, update the `__init__.py` inside the `models` folder to import `todo_model`:

### `models/__init__.py`
```python
from . import todo_model
```

Once you've set up these files, update the module list in Odoo and install your new module. You'll see a new menu item "To-Do Tasks" where you can add and manage tasks.
