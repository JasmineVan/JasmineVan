<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello World</title>
</head>

<body>
    <div id="container"></div>
    <script type="module">
        import * as THREE from "./three.module.js"
        // Create scene of the project
        var scene = new THREE.Scene();
        // Background image
        const bgImageTexture = new THREE.TextureLoader().load("./Images/gradient1.jpg");
        bgImageTexture.wrapS = THREE.RepeatWrapping;
        bgImageTexture.wrapT = THREE.RepeatWrapping;
        // bgImageTexture.repeat.set(4, 4);
        scene.background = bgImageTexture;
        
        // Linear color
        // scene.background = new THREE.Color( 0xf8c4b4 );
        
        // scene.background = null
        // Camera
        var width = window.innerWidth;
        var height = window.innerHeight;
        var viewAngle = 45;
        var nearClipping = 0.1;
        var farClipping = 9999;

        var camera = new THREE.PerspectiveCamera(viewAngle, width / height, nearClipping, farClipping);
        camera.position.set(0, 0, 10)

        // Cube 1
        var cubeGeometry = new THREE.BoxGeometry(1, 1, 1)
        var cubeMaterial1 = new THREE.MeshBasicMaterial({ color: 0xFEFBE9 })
        var cubeMaterial2 = new THREE.MeshBasicMaterial({ color: 0x6f3be4 })
        var cubeMaterial3 = new THREE.MeshBasicMaterial({ color: 0xF0A04B })
        var cubeMaterial4 = new THREE.MeshBasicMaterial({ color: 0x183A1D })
        var cubeMaterial5 = new THREE.MeshBasicMaterial({ color: 0xD61355 })
        var cubeMaterial6 = new THREE.MeshBasicMaterial({ color: 0xF94A29 })
        var cubeMaterial7 = new THREE.MeshBasicMaterial({ color: 0xFCE22A })
        var cubeMaterial8 = new THREE.MeshBasicMaterial({ color: 0x30E3DF })
        var cubeMaterial9 = new THREE.MeshBasicMaterial({ color: 0x1F8A70 })

        var cube1 = new THREE.Mesh(cubeGeometry, cubeMaterial1)
        var cube2 = new THREE.Mesh(cubeGeometry, cubeMaterial2)
        var cube3 = new THREE.Mesh(cubeGeometry, cubeMaterial3)
        var cube4 = new THREE.Mesh(cubeGeometry, cubeMaterial4)
        var cube5 = new THREE.Mesh(cubeGeometry, cubeMaterial5)
        var cube6 = new THREE.Mesh(cubeGeometry, cubeMaterial6)
        var cube7 = new THREE.Mesh(cubeGeometry, cubeMaterial7)
        var cube8 = new THREE.Mesh(cubeGeometry, cubeMaterial8)
        var cube9 = new THREE.Mesh(cubeGeometry, cubeMaterial9)

        cube1.position.set(-5, 3, 0)
        cube2.position.set(0, 3, 0)
        cube3.position.set(5, 3, 0)
        cube4.position.set(-5, 0, 0)
        cube5.position.set(0, 0, 0)
        cube6.position.set(5, 0, 0)
        cube7.position.set(-5, -3, 0)
        cube8.position.set(0, -3, 0)
        cube9.position.set(5, -3, 0)
        scene.add(cube1, cube2, cube3, cube4, cube5, cube6, cube7, cube8, cube9)

        // Renderer part
        var renderer = new THREE.WebGLRenderer({ antialize: true });
        renderer.setSize(width, height);

        // JS to get element
        var element = document.getElementById("container")
        element.appendChild(renderer.domElement);

        // background image

        // Animation
        function animate() {
            // Rotate cube
            cube1.rotation.x += 0.01
            cube2.rotation.y += 0.01

            cube3.rotation.z += 0.01
            cube4.rotation.x += 0.01

            cube5.rotation.y += 0.01
            cube6.rotation.z += 0.01
            cube7.rotation.z += 0.01

            cube8.rotation.y += 0.01
            cube9.rotation.z += 0.01

            requestAnimationFrame(animate);

            renderer.render(scene, camera);
        }
        animate();
    </script>
</body>

</html>
