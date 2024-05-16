Vagrant.configure("2") do |config|
  
  # Introduce aquí la configuración del servidor virtual
  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.50.55"

   # Configuracion de las carpetas sincronizadas
   config.vm.synced_folder ".", "/vagrant_data"

  config.vm.provision "shell", inline: <<-SHELL

      # Instalación de los binarios de PHP, el driver mysqli y la extensión FPM para realizar peticiones de tipo RESTful
      sudo apt-get update
      sudo apt-get install -y mysql-server

      sudo apt-get install -y nginx

      sudo apt-get install -y php php-mysql php-fpm

      # Creamos la base de datos y la tabla de empleados
      

      # Generar archivo SQL con los registros de los diferentes Módulos Profesionales
      echo "-- Insertar datos de ejemplo en la tabla 'empleados'" > /home/vagrant/datos_empleados.sql
      echo "INSERT INTO gestion_empleados.empleados (nombre, apellido, edad, salario, departamento) VALUES" >> /home/vagrant/datos_empleados.sql
      echo "('Miguel', 'Cueto', 30, 2500.00, 'Ventas')," >> /home/vagrant/datos_empleados.sql
      echo "('Manolo', 'Alonso', 40, 2000.00, 'Desarrollo')," >> /home/vagrant/datos_empleados.sql
      echo "('Raquel', 'Carril', 50, 1000.00, 'Ventas')," >> /home/vagrant/datos_empleados.sql
      echo "('Teresa', 'Molina', 10, 2400.00, 'Marketing')," >> /home/vagrant/datos_empleados.sql
      echo "('Pepe', 'Couce', 20, 2500.00, 'Ventas');" >> /home/vagrant/datos_empleados.sql

  SHELL

end
