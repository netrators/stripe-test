import React, { useState, useEffect } from 'react';

// ==========================================
// ⚠️ INSTRUCCIONES PARA GITHUB ⚠️
// 1. Instala en tu proyecto: npm install @stripe/stripe-js @stripe/react-stripe-js
// 2. Descomenta las siguientes dos líneas y borra la sección de MOCKS:
// import { loadStripe } from '@stripe/stripe-js';
// import { Elements, PaymentElement, useStripe, useElements } from '@stripe/react-stripe-js';
// ==========================================

// --- MOCKS PARA LA VISTA PREVIA EN CANVAS (BORRAR AL SUBIR A GITHUB) ---
// (Estas funciones simulan a Stripe para que el entorno pueda compilar visualmente)
const loadStripe = () => Promise.resolve({});
const Elements = ({ children }) => <div className="stripe-mock-container">{children}</div>;
const PaymentElement = () => (
  <div className="w-full h-12 bg-white border border-slate-300 rounded-md px-4 flex items-center justify-between text-sm shadow-sm font-mono mt-2 mb-4">
    <span className="text-slate-800 tracking-widest">•••• •••• •••• ••••</span>
    <div className="flex space-x-6">
      <span className="text-slate-400">MM/AA</span>
      <span className="text-slate-400">CVC</span>
    </div>
  </div>
);
const useStripe = () => ({
  confirmPayment: async ({ confirmParams }) => {
    return new Promise((resolve) => {
      setTimeout(() => {
        window.location.href = confirmParams.return_url;
        resolve({});
      }, 1500);
    });
  }
});
const useElements = () => ({});
// -------------------------------------------------------------

// ==========================================
// ⚠️ INSTRUCCIONES DE SEGURIDAD ⚠️
// 1. Reemplaza 'pk_test_TU_CLAVE_AQUI' con tu clave PÚBLICA de Stripe.
// 2. NUNCA pongas tu clave secreta (sk_test_...) en este archivo.
// ==========================================
const stripePromise = loadStripe('pk_test_TU_CLAVE_AQUI');

// --- COMPONENTE 1: FORMULARIO DE STRIPE ---
const CheckoutForm = ({ clientSecret }) => {
  const stripe = useStripe();
  const elements = useElements();
  const [isLoading, setIsLoading] = useState(false);
  const [errorMessage, setErrorMessage] = useState(null);

  const handleSubmit = async (e) => {
    e.preventDefault();
    if (!stripe || !elements) return;

    setIsLoading(true);
    setErrorMessage(null);

    // Stripe confirmará el pago usando el Elemento que está en pantalla
    const { error } = await stripe.confirmPayment({
      elements,
      confirmParams: {
        // Stripe redirigirá aquí tras un pago exitoso
        return_url: window.location.origin + "?success=true", 
      },
    });

    if (error) {
      // Si hay error (ej. fondos insuficientes), se muestra al usuario
      setErrorMessage(error.message);
    }
    setIsLoading(false);
  };

  return (
    <form onSubmit={handleSubmit} className="space-y-6">
      <div className="p-4 bg-slate-50 border border-slate-200 rounded-lg">
         <PaymentElement options={{layout: 'tabs'}} />
      </div>

      <button 
        disabled={isLoading || !stripe || !elements}
        className="w-full bg-teal-600 hover:bg-teal-700 text-white font-bold py-4 px-4 rounded-lg transition-colors flex justify-center items-center disabled:opacity-70 disabled:cursor-not-allowed shadow-md shadow-teal-600/20"
      >
        {isLoading ? (
          <span className="flex items-center">
            <svg className="animate-spin -ml-1 mr-3 h-5 w-5 text-white" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
              <circle className="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" strokeWidth="4"></circle>
              <path className="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
            </svg>
            Procesando pago...
          </span>
        ) : (
          "Pagar $500.00 MXN"
        )}
      </button>

      {errorMessage && (
        <div className="bg-red-50 border-l-4 border-red-500 p-4 rounded-md">
          <p className="text-sm text-red-700">{errorMessage}</p>
        </div>
      )}
      
      <p className="text-xs text-slate-400 text-center flex items-center justify-center mt-4">
        <svg className="w-4 h-4 mr-1" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path></svg>
        Transacción segura encriptada por Stripe.
      </p>
    </form>
  );
};

// --- COMPONENTE PRINCIPAL (VISTA) ---
export default function App() {
  const [clientSecret, setClientSecret] = useState("");
  const [isSuccessMode, setIsSuccessMode] = useState(false);

  useEffect(() => {
    // Verificar si venimos de un pago exitoso (redirección de Stripe)
    const query = new URLSearchParams(window.location.search);
    if (query.get("success")) {
      setIsSuccessMode(true);
      return;
    }

    // ==========================================
    // MODO PRUEBA / SIMULACIÓN DE BACKEND
    // En producción, aquí harías un fetch a tu servidor/Supabase
    // para obtener un clientSecret real. 
    // Para que puedas ver el diseño sin backend, usamos un truco:
    // Hacemos que el UI espere como si estuviera cargando, pero
    // notarás que los campos de Stripe no aparecerán hasta que 
    // le pongas un client_secret válido de prueba.
    // ==========================================
    
    // Simulación de carga del backend
    const simulateBackendFetch = setTimeout(() => {
       // Pega aquí un 'pi_test_..._secret_...' que hayas generado 
       // manualmente en tu panel de Stripe para ver los campos reales
       const secretDePrueba = ""; 
       if(secretDePrueba) setClientSecret(secretDePrueba);
    }, 1500);

    return () => clearTimeout(simulateBackendFetch);
  }, []);

  // Configuración de colores para el iframe de Stripe
  const stripeAppearance = {
    theme: 'stripe',
    variables: {
      colorPrimary: '#0d9488', // teal-600
      colorBackground: '#ffffff',
      colorText: '#0f172a', // slate-900
      colorDanger: '#ef4444',
      fontFamily: 'system-ui, sans-serif',
      spacingUnit: '4px',
      borderRadius: '8px',
    },
  };

  if (isSuccessMode) {
    return (
      <div className="min-h-screen bg-slate-50 flex items-center justify-center p-4 font-sans">
        <div className="max-w-md w-full bg-white rounded-xl shadow-lg border border-slate-100 p-8 text-center">
          <div className="w-20 h-20 bg-teal-50 rounded-full flex items-center justify-center mx-auto mb-6">
            <svg className="w-10 h-10 text-teal-600" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth="2" d="M5 13l4 4L19 7"></path>
            </svg>
          </div>
          <h2 className="text-2xl font-bold text-slate-900 mb-2">¡Pago Exitoso!</h2>
          <p className="text-slate-600 mb-8">
            Tu acceso a las <strong>Guías de Estudio</strong> ha sido habilitado correctamente en el sistema.
          </p>
          <button 
            onClick={() => window.location.href = window.location.origin}
            className="w-full bg-slate-900 hover:bg-slate-800 text-white font-semibold py-3 px-4 rounded-lg transition-colors"
          >
            Volver al Inicio
          </button>
        </div>
      </div>
    );
  }

  return (
    <div className="min-h-screen bg-slate-50 flex items-center justify-center p-4 font-sans">
      <div className="max-w-4xl w-full flex flex-col md:flex-row bg-white rounded-2xl shadow-xl overflow-hidden border border-slate-200">
        
        {/* PANEL IZQUIERDO: Resumen */}
        <div className="w-full md:w-1/3 bg-slate-900 p-8 text-white flex flex-col justify-between">
          <div>
            <h2 className="text-xl font-bold text-teal-400 mb-6">Colegio Tepic</h2>
            <div className="mb-8">
              <p className="text-slate-400 text-sm uppercase tracking-wider mb-1">Concepto</p>
              <h3 className="text-2xl font-semibold">Guías de Estudio - Ciclo 2024</h3>
            </div>
            
            <div className="space-y-4 text-sm text-slate-300 mb-8">
              <div className="flex justify-between border-b border-slate-700 pb-2">
                <span>Material descargable</span>
                <span className="text-white">Incluido</span>
              </div>
              <div className="flex justify-between border-b border-slate-700 pb-2">
                <span>Acceso a plataforma</span>
                <span className="text-white">Anual</span>
              </div>
            </div>
          </div>
          
          <div>
            <p className="text-slate-400 text-sm mb-1">Total a pagar</p>
            <p className="text-4xl font-bold text-white">$500.00 <span className="text-lg font-normal text-teal-400">MXN</span></p>
          </div>
        </div>

        {/* PANEL DERECHO: Stripe Elements */}
        <div className="w-full md:w-2/3 p-8 md:p-12">
          <h2 className="text-2xl font-bold text-slate-900 mb-2">Detalles de pago</h2>
          <p className="text-slate-500 mb-8">Selecciona tu método de pago preferido. Aceptamos tarjetas y pagos en efectivo (OXXO).</p>
          
          {clientSecret ? (
            <Elements options={{ clientSecret, appearance: stripeAppearance }} stripe={stripePromise}>
              <CheckoutForm clientSecret={clientSecret} />
            </Elements>
          ) : (
            <div className="text-center py-12 bg-slate-50 rounded-lg border border-dashed border-slate-300">
              <div className="animate-pulse flex flex-col items-center">
                <div className="h-8 w-8 bg-slate-200 rounded-full mb-4"></div>
                <p className="text-slate-500 font-medium">Conectando con el servidor seguro...</p>
                <p className="text-xs text-slate-400 mt-2 max-w-xs mx-auto">
                  (En un entorno real, aquí se muestra el formulario de Stripe tras recibir el token del backend)
                </p>
              </div>
            </div>
          )}
        </div>
      </div>
    </div>
  );
}
