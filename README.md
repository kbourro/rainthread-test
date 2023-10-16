1) Εξετάστε τον παρακάτω κώδικα και προσπαθήστε να εντοπίσετε και να διορθώσετε τα λάθη.
```
import React, { useState } from 'react';

function Counter() {
    const [count, setCount] = useState(0);

    function increaseCount() {
        count = count + 1;
    }

    return (
        <div>
            <p>Τρέχων σκορ: {count}</p>
            <button onClick={increaseCount}>Αύξηση</button>
        </div>
    );
}
```
2) Εξετάστε τον παρακάτω κώδικα και εντοπίστε το πρόβλημα με τα περιττά rerenders. Διορθώστε το.
```
import React, { useState } from 'react';

function ItemList() {
    const [items, setItems] = useState(['Αντικείμενο 1', 'Αντικείμενο 2']);
    const newItems = [...items, 'Νέο Αντικείμενο'];

    function addItem() {
        setItems(newItems);
    }

    return (
        <div>
            <ul>
                {items.map(item => <li key={item}>{item}</li>)}
            </ul>
            <button onClick={addItem}>Προσθήκη Αντικειμένου</button>
        </div>
    );
}
```
3) Έχετε τον παρακάτω κώδικα React που δείχνει το τρέχον σκορ. Μετατρέψτε τον κώδικα ώστε να χρησιμοποιεί το Redux Toolkit για τη διαχείριση της κατάστασης.
```
import React, { useState } from 'react';

function Score() {
    const [score, setScore] = useState(0);

    return (
        <div>
            <p>Τρέχον σκορ: {score}</p>
            <button onClick={() => setScore(score + 1)}>Αύξηση</button>
        </div>
    );
}
```
4) Δεδομένου του παρακάτω κώδικα, βελτιώστε τον ώστε να ελαχιστοποιήσετε τα περιττά rerenders χρησιμοποιώντας το useCallback.
```
import React, { useState } from 'react';

function ButtonComponent({ onClick }) {
    console.log('ButtonComponent rerendered!');
    return <button onClick={onClick}>Κάντε κλικ!</button>;
}

function TestComponent() {
    const [count, setCount] = useState(0);

    function handleClick() {
        setCount(count + 1);
    }

    return (
        <div>
            <p>Κλικς: {count}</p>
            <ButtonComponent onClick={handleClick} />
        </div>
    );
}
```
5) Δεδομένου του παρακάτω κώδικα, βελτιώστε τον ώστε να υπολογίζεται η λίστα των τετραγωνικών ριζών μόνο όταν αλλάζει η λίστα των αριθμών, χρησιμοποιώντας το useMemo.
```
import React, { useState } from 'react';

function ListComponent({ numbers }) {
    const squaredNumbers = numbers.map(num => Math.sqrt(num));
    console.log('Computed squared numbers!');

    return (
        <ul>
            {squaredNumbers.map((num, index) => <li key={index}>{num}</li>)}
        </ul>
    );
}

function TestComponent() {
    const [numbers, setNumbers] = useState([1, 4, 9, 16]);

    return (
        <div>
            <ListComponent numbers={numbers} />
            <button onClick={() => setNumbers([...numbers, 25])}>Προσθήκη 25</button>
        </div>
    );
}
```
