# york_solutions_sql
solution to York Solutions IT SQL related challenge/assessment


When attempting to complete this solution on the browser-based SQL interpreter supplied by York Solutions, the solutions I created to their assessment failed despite crafting three working versions of the code for the command block that keeps crashing the code.


### Solution Attempt 1:
    UPDATE contact as c
        SET cellphone = 4383991212
            FROM employee as e
                WHERE c.id=e.id AND e.fName='Susan' AND e.lName = 'Shepard';

### Solution Attempt 2:
    UPDATE contact as c
        SET cellphone = 4383991212
    FROM employee e
        WHERE fName=( SELECT fName
            FROM employee as e
                inner join contact c
                    on c.id = e.id
                        where e.fName='Susan');

### Solution Attempt 3:
    UPDATE contact 
        SET cellphone = 4383991212
    FROM employee 
        WHERE fName='Susan' AND lName='Shepard';

Each of these solutions deliver the following error message
> SyntaxError: Parse error on line 105: ...phone = 4383991212 FROM employee WHER ----------------------^ Expecting 'EOF', 'COMMA', 'RPAR', 'IN', 'LIKE', 'ARROW', 'DOT', 'CARET', 'EQ', 'WHERE', 'SLASH', 'EXCLAMATION', 'MODULO', 'GT', 'LT', 'GTGT', 'LTLT', 'NOT', 'AND', 'OR', 'PLUS', 'STAR', 'END', 'WHEN', 'ELSE', 'REGEXP', 'TILDA', 'GLOB', 'NOT_LIKE', 'BARBAR', 'MINUS', 'AMPERSAND', 'BAR', 'GE', 'LE', 'EQEQ', 'EQEQEQ', 'NE', 'NEEQEQ', 'NEEQEQEQ', 'BETWEEN', 'NOT_BETWEEN', 'IS', 'DOUBLECOLON', 'OUTPUT', 'GO', 'SEMICOLON', got 'FROM'


Why their SQL interpreter crashes when mine doesn't is a mystery, and I hope to address this issue in the technical interview.