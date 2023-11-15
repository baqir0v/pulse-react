import './header.scss';
import Phone from "../../assets/Phone.svg";
import { useState } from 'react';

function Header() {
    const [firstImg, setfirstImg] = useState("https://preview.colorlib.com/theme/pulse/img/slider/slider-1.jpg.webp");
    const [secondImg, setsecondImg] = useState("https://preview.colorlib.com/theme/pulse/img/slider/slider-2.jpg.webp");
    const [thirdImg, setthirdImg] = useState("https://preview.colorlib.com/theme/pulse/img/slider/slider-3.jpg.webp");
    const [currentImg, setcurrentImg] = useState(firstImg);

    const [isNavOpen,setIsNavOpen] = useState(false);
    function handleNavbar() {
        setIsNavOpen(!isNavOpen)
    }

    const [color, setcolor] = useState("white");
    const [newcolor, setnewcolor] = useState("#ffc515");


    const handleButtonClick = (newImg, newcolor) => {
        setcurrentImg(newImg);
        setcolor(newcolor);
    };

    

    return (

        <header style={{ backgroundImage: `url(${currentImg})` }} id='header'>
            <div className={`${isNavOpen ? "dnone" : "tabs"}`}>
                <ul>
                    <li>1</li>
                    <li>2</li>
                    <li>3</li>
                    <li>4</li>
                    <li>5</li>
                </ul>
            </div>
            <nav id='navbar'>
                <div className='navbox1'>
                    <h2>Pulse<span>.</span></h2>
                </div>
                <div className='navbox2'>
                    <ul>
                        <li>Home</li>
                        <li>About US</li>
                        <li>Restaurant</li>
                        <li>News</li>
                        <li>Contact</li>
                    </ul>
                </div>
                <div className='navbox3'>
                    <p><span>Reservations</span> <img src={Phone} alt="" />  652-345 3222 11</p><i className="fa-solid fa-bars" onClick={handleNavbar}></i>
                </div>
            </nav>
            <div className='hbottom'>

                <div className='numbers'>
                    <div className="dots" style={{ color: color }}>01.</div>
                    <div className="dots" style={{ color: color }}>02.</div>
                    <div className="dots" style={{ color: color }}>03.</div>
                </div>
                <div className='headerbox'>
                    <h2>Special Dish<span>.</span></h2>
                    <p>By Chef Francis Smith</p>
                    <div className='buttons'>
                        <button onClick={() => handleButtonClick(firstImg, newcolor)}></button>
                        <button onClick={() => handleButtonClick(secondImg, newcolor)}></button>
                        <button onClick={() => handleButtonClick(thirdImg, newcolor)}></button>
                    </div>
                </div>
            </div>
        </header>
    );
}

export default Header;
