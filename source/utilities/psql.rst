Psql
####

Qué es psql
-----------

`Psql` es la terminal interactiva para trabajar con Postgres. Hay muchas
opciones disponibles para usar cuando trabajas con psql, pero nos enfocaremos
en los más importantes, como conectarse:

- -h el host a conectarse
- -U usuario de conexión
- -P el puerto a conectarse (por defecto es 5432)

.. code-block:: console

   psql -h localhost -U usuario base_de_datos

La otra opción es usar una cadena de texto y dejar a psql que la traduzca:

.. code-block:: console

    psql "dbname=dbhere host=hosthere user=userhere password=pwhere port=5432 sslmode=require"

Una vez que estas conectado puedes empezar a consultar. A más de consultas
básicas puedes usar ciertos comandos. Ejecutando `\?` te dará una lista de
los comandos disponibles, piensa en algunas claves will give you a list 
of all available commands, algunas palabras claves son utilizadas a más de los tips.

Tips
----

Listar tablas de la base de datos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code-block:: console

   # \d
         List of relations
    Schema |   Name    | Type  | Owner 
   --------+-----------+-------+-------
    public | employees | table | craig
   (1 row)


Describir una tabla
~~~~~~~~~~~~~~~~~~~

.. code-block:: console

   # \d employees 
              Table "public.employees"
     Column   |         Type          | Modifiers 
   -----------+-----------------------+-----------
    id        | integer               | 
    last_name | character varying(50) | 
    salary    | integer               | 
   Indexes:
       "idx_emps" btree (salary)
