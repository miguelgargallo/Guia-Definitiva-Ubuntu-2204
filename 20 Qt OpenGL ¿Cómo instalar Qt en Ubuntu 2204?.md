 0 Qt OpenGL ¿Cómo instalar Qt en Ubuntu 2204?

Insertamos este link para descargar el instalador, este es el último Qt 5 que hay a fecha de 9 de Octubre del 2022

    wget https://download.qt.io/new_archive/qt/5.11/5.11.3/qt-opensource-linux-x64-5.11.3.run

Le damos permisos

    chnmod +x qt-opensource-linux-x64-5.11.3.run

Ejecutamos el .run

    ./qt-opensource-linux-x64-5.11.3.run
    
O básicamente ejecutas esto en vez de todo lo anterior

    sudo apt-get install qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools

Si nos faltan headers en C++ añadimos esto en nuestra terminal para que VS Code lo canalize correctamente

    g++ main.cpp -lGL -lglut -lGLEW -I/path/to/glm/headers

Ejecutar nuestro OpenGL con un solo comando

   qmake && make && ./nombreDelEjecutable
   
  
