Main.jsx
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./index.css";

ReactDOM.createRoot(document.getElementById("root")).render(
    <React.StrictMode>
        <App />
    </React.StrictMode>
);

App.jsx
import Contador from "./components/Contador";

function App() {
    return <Contador />;
}

export default App;

Alerta.jsx
function Alerta ({ mensaje}) {
    return (
        <div className="mt-4 bg-red-100 text-red-700 p-3 rounded-lg text-center">
        {mensaje}
        </div>
    );
}

Contador.jsx
import { useState } from "react";
import Alerta from "./Alerta";

function Contador() {
    const [contador, setContador] =useState(0);
    const [mensajeError, setMensajeError] = useState("");

    const incrementar = () => {
        setMensajeError("");
        setContador(contador + 1);
    };

    const decrementar = () => {
        if (contador === 0) {
            setMensajeError("No se puede disminuir mas, El contador esta en 0.");
            return;
        }

        setMensajeError("");
        setContador(contador - 1);
    };

    const reiniciar = () => {
        setMensajeError("");
        setContador(0);
    };

    return (
        <div className="min-h-screen bg-gray-100 flex items-center justify-center">
        <div className="bg-white p-8 rounded-2xl shadow-lg w-96 text-center">
        <h1 className="text-2xl font-bold mb-6">
            Contador de clics
        </h1>

        <p className="text--5xl font-bold mb-6 ">
            <button 
            onClick ={incrementar}
            className="bg-green-500 text-white px-4 py-2 rounded-lg hover:bg-green-600 transition"
            >
                Incrementar
            </button>

            onClick={descrementar}
            className="bg-red-500 text-white px-4 py-2 rounded-lg horver:bg-re-600 transition"
            >
             Disminuir 
             </button>

             </button>
             onClick={reiniciar}
             className="bg-red-500 text-white px-4 py-2 rounded-lg horver:bg-re-600 trnsition "
             
             >
               Reiniciar
               </button>
               </div>

             </div>
    );
}

export default Contador;

CodigoCompleto,jsx
import { useState } from "react";

function App() {
  const [contador, setContador] = useState(0);
  const [mensajeError, setMensajeError] = useState("");

  const incrementar = () => {
    setMensajeError("");
    setContador(contador + 1);
  };

  const disminuir = () => {
    if (contador === 0) {
      setMensajeError("No se puede disminuir más. El contador ya está en 0.");
      return;
    }

    setMensajeError("");
    setContador(contador - 1);
  };

  const reiniciar = () => {
    setMensajeError("");
    setContador(0);
  };

  return (
    <div className="min-h-screen bg-gray-100 flex items-center justify-center">
      <div className="bg-white p-8 rounded-2xl shadow-lg w-96 text-center">
        <h1 className="text-2xl font-bold mb-6">
          Contador de Clics
        </h1>

        {/* Mostrar contador */}
        <p className="text-5xl font-bold mb-6">
          {contador}
        </p>

        {/* Botones */}
        <div className="flex flex-col gap-3">
          <button
            onClick={incrementar}
            className="bg-green-500 text-white py-2 rounded-lg hover:bg-green-600 transition"
          >
            Incrementar
          </button>

          <button
            onClick={disminuir}
            className="bg-red-500 text-white py-2 rounded-lg hover:bg-red-600 transition"
          >
            Disminuir
          </button>

          <button
            onClick={reiniciar}
            className="bg-gray-500 text-white py-2 rounded-lg hover:bg-gray-600 transition"
          >
            Reiniciar
          </button>
        </div>

        {/* Alerta personalizada */}
        {mensajeError && (
          <div className="mt-4 bg-red-100 text-red-700 p-3 rounded-lg">
            {mensajeError}
          </div>
        )}
      </div>
    </div>
  );
}

export default App;
