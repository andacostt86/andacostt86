@@ -0,0 +1,10 @@
- importar  titiritero  desde  'titiritero' ;

 navegador  const =  espera  titiritero . lanzamiento ( { sin cabeza : 'nuevo' } ) ;
 página  constante =  esperar  navegador . nueva pagina ( ) ;
 sesión  constante =  esperar  página . objetivo ( ) . crearCDPSession ( ) ;

 URL  constante =  'https://leverx.com/' ;

 solicitudes  constantes =  [ ] ;
sesión . on ( 'Network.requestWillBeSent' ,  e  =>  solicitudes . push ( e ) ) ;
esperando  sesión . enviar ( 'Red.habilitar' ) ;

espera  la página . ir a ( url ) ;

 solicitud  constante =  solicitudes . buscar ( r  =>  r . solicitud . url  ===  url ) ;
const  { solicitudId }  =  solicitud ;

const  { cuerpo }  =  esperar  sesión . enviar ( 'Network.getResponseBody' ,  { solicitudId } ) ;
consola . registro ( cuerpo ) ;

Espera  al navegador . cerca ( ) ;
