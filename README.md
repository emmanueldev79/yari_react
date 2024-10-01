# yari_react

1. La diferencia entre un componente UI y un functional component, esta en que el functional component ademas de renderizar jsx maneja la logica y el estado. mientras que el componente de UI es solo presentacional, y se usan las props tambien

```javascript
import React from "react";
import React, { useState } from "react";

const Saludo = ({ nombre }) => {
const [info, setInfo] = useState("");
  return (
    <div>
      <h1>¡Hola, {nombre}!</h1>
      <p>Bienvenido/a a nuestra aplicación. <button onClick={()=>setInfo("Nueva info")}>cambiar parrafo</button></p>
    </div>
  );
};

export default Saludo;
```

2. Las props, es un concepto que permite que diferentes componenetes se comuniquen entre si

```javascript
import React from "react";

const Saludo = ({ nombre, idioma }) => {
  return (
    <div>
      <h1>¡Hola, {nombre}!</h1>
      <p>{idioma}.</p>
    </div>
  );
};

export default Saludo;
```

3. Children props, se usan para reutilizacion y organizacion del codigo

```javascript
import React from "react";
import "./Contenedor.css";

const Contenedor = ({ children }) => {
  return <div className="contenedor">{children}</div>;
};

export default Contenedor;
```

```css
.contenedor {
  border: 2px solid #007bff;
  padding: 16px;
  border-radius:
  margin: 16px;
}
```

4. useState, es un hook de react para manejar el estado de manera local en functional components, en el ejemplo uso el concepto de children

```javascript
import React, { useState } from "react";
import Contenedor from "./Contenedor";
const Contador = () => {
  const [contador, setContador] = useState(0);

  return (
    <Contenedor>
      <h1>Contador: {contador}</h1>
      <button onClick={() => setContador(contador + 1)}>Incrementar</button>
      <button onClick={() => setContador(contador - 1)}>Decrementar</button>
    </Contenedor>
  );
};

export default Contador;
```
