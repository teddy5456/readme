  +-----------------------+         +------------------+
  |        User           |         |   CleaningPlan   |
  +-----------------------+         +------------------+
  | id: integer (PK)      |         | id: integer (PK) |
  | name: string          |         | name: string     |
  | email: string         |         | description: text|
  | password_digest: string |         | price: decimal   |
  | role: string          |         +------------------+
  +-----------------------+

         |  ^                            ^
         |  |                            |
         |  |                            |
         |  |                            |
         |  |                            |
         |  |                            |
         v  |                            |
  +----------------+         +-------------------+
  |    Review      |         |     Cleaner       |
  +----------------+         +-------------------+
  | id: integer(PK)|         | id: integer (PK)  |
  | rating: integer |         | name: string     |
  | comment: text   |         | specialization: string |
  | user_id: integer(FK)|     +-------------------+
  | cleaner_id: integer(FK)|         |
  +-----------------------+         |
                                    |
                                    |
                                    |
                                    v
                          +----------------------+
                          |   CleaningRequest    |
                          +----------------------+
                          | id: integer (PK)     |
                          | user_id: integer (FK)|
                          | cleaner_id: integer (FK)|
                          | accepted: boolean    |
                          | deleted: boolean     |
                          +----------------------+
