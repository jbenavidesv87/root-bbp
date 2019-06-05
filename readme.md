<!DOCTYPE html>
<html>
  <head>
    <!--Import Google Icon Font-->
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
    <!--Import materialize.css-->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/css/materialize.min.css">
    <style>
        .container{
            padding-top: 56px;
        }
        .f1_container {
            position: relative;
            width: 45px;
            height: 45px;
            z-index : 1;
            float:left;
        }
        .f1_container {
            -webkit-perspective: 1000;
            perspective: 1000;
        }
        .f1_card {
            width: 100%;
            height: 100%;
            -webkit-transform-style: preserve-3d;
            -webkit-transition: all 0.2s linear;
            transform-style: preserve-3d;
            transition: all 0.2s linear;
        }
        .f1_container.active .f1_card {
            -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
        }
        .face {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            -webkit-backface-visibility: hidden;
        }
        .face.back {
            display: block;
            -webkit-transform: rotateY(180deg);
            transform: rotateY(180deg);
            box-sizing: border-box;
            text-align: center;
        }
    </style>

    <!--Let browser know website is optimized for mobile-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  </head>

  <body>
        <div class="navbar-fixed">
            <nav class="nav-extended">
                <div class="nav-wrapper">
                <a href="#!" class="brand-logo">ROOT - BBP</a>
                <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
                <ul class="right hide-on-med-and-down">
                    <li><a href="#setup">Setup</a></li>
                    <li><a href="#rules">Rules</a></li>
                    <li><a href="#victory">Victory</a></li>
                    <li><a href="#clearing">Clearing priority</a></li>
                    <li><a href="#items">Items</a></li>
                    <li><a href="#buildings">Buildings</a></li>
                    <li><a href="#turn">Turn</a></li>
                </ul>
                </div>
                <div class="nav-content">
                        <ul class="tabs tabs-transparent">
                            <li class="tab"><a class="active" href="#test1">Mechanical Marquise</a></li>
                            <li class="tab"><a href="#test2">Later</a></li>
                            <li class="tab disabled"><a href="#test3">Later</a></li>
                            <li class="tab"><a href="#test4">Later</a></li>
                        </ul>
                    </div>
            </nav>
        </div>
        <ul class="sidenav" id="mobile-demo">
            <li><a href="#setup">Setup</a></li>
            <li><a href="#rules">Rules</a></li>
            <li><a href="#victory">Victory</a></li>
            <li><a href="#clearing">Clearing</a></li>
            <li><a href="#items">Items</a></li>
            <li><a href="#buildings">Buildings</a></li>
            <li><a href="#turn">Turn</a></li>
        </ul>
      <div class="container">

            <div class="card-panel">
                <h5><a name="setup"></a>Setup (A)</h5>
                <ol>
                    <li>Place the keep token in a random corner clearing.</li>
                    <li>Place 1 warrior in each clearing, except the corner clearing diagonally opposite from the keep. Add an additional warrior to the clearing with the keep token. <small>Place 12 warriors in total.</small></li>
                    <li>Place 1 sawmill, workshop and recruiter randomly among the clearings adjacent to the keep token. <small>Place 3 in total, 1 per clearing.</small></li>
                </ol>
                <div class="row">
                    <div class="col">
                        <h6>Difficulty</h6>
                        <ul class="tabs">
                            <li class="tab col"><a href="#easy" class="active">Easy</a></li>
                            <li class="tab col"><a href="#norm" class="active">Normal</a></li>
                            <li class="tab col"><a href="#normal">Challenging</a></li>
                            <li class="tab col"><a id="hardTab" href="#hard">Nightmare</a></li>
                        </ul>
                    </div>
                    <div class="col">
                        <h6>Map</h6>
                        <ul class="tabs">
                            <li class="tab col"><a href="#forest" class="active">Forest</a></li>
                            <li class="tab col"><a href="#winter" class="active">Winter</a></li>
                        </ul>
                    </div>
                    <div class="col">
                        <h6>Traits</h6>
                        <p>
                            <label>
                                <input type="checkbox" class="filled-in" value="blitz" />
                                <span>Blitz</span>
                            </label>
                        </p>
                        <p>
                            <label>
                                <input type="checkbox" class="filled-in" value="fortified"/>
                                <span>Fortified</span>
                            </label>
                        </p>
                        <p>
                            <label>
                                <input type="checkbox" class="filled-in" value="ironwill"/>
                                <span>Iron Will</span>
                            </label>
                        </p>
                        <p>
                            <label>
                                <input type="checkbox" class="filled-in" value="hospitals"/>
                                <span>Hospitals</span>
                            </label>
                        </p>
                    </div>
                </div>
            </div>

            <div class="card-panel">
                <h5><a name="rules"></a>Rules</h5>
                <div class="row">
                    <div class="col m6">
                        <h6>Poor Manual Dexerity</h6>
                        <p>The Mechanical Marquise has no hand of cards. It cannot discard cards. If a player is prompted to take a card from the Mechanical Marquise, they draw a card instead. If prompted to give it a card, discard the card, and it scores +1.</p>
                    </div>
                    <div class="col m3">
                        <h6>Hates Surprises</h6>
                        <p>Ambush cards cannot be played against bots.</p>
                    </div>
                    <div class="col m3">
                        <h6>The Keep</h6>
                        <p>Only you can place pieces in the clearing with the keep token.</p>
                    </div>
                </div>
                <div class="row">
                    <div class="col m6" id="fortified">
                        <h6>Fortified</h6>
                        <p>Opponents require 1 hits to destroy each of your buildings. Assigning a single hit to a building has no effect.</p>
                    </div>
                    <div class="col m6" id="hospitals">
                        <h6>Hospitals</h6>
                        <p>After each battle as Defender in which you lost at least 2 warriors, immediately recruit 1 warrior in the clearing warrior in the clearing with the keep token.</p>
                    </div>
                </div>
            </div>

            <div class="card-panel">
                <div class="row">
                    <div class="col m4">
                        <h5><a name="clearing"></a>Clearing Priority</h5>
                        <p><small>Highest priority is 1, lowest priority is 12.</small></p>
                        <img id="forest" src="images/forest.png" style="max-width: 100%">
                        <img id="winter" src="images/winter.png" style="max-width: 100%">

                        <h5><a name="victory"></a>Victory points</h5>
                        <input id="bag" type="number" min="0" value="0">
                        <label for="bag">Points</label>
                    </div>
                    <div class="col m8">
                        <h5  name="items">Items for sale</h5>
                        <p><small>Vagabond can give cards to take these items</small></p>
                        <form>
                            <div class="row">
                                <div class="input-field col s4 m3">
                                    <input id="bag" type="number" min="0" value="0">
                                    <label for="bag">Bags</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="boot" type="number" min="0" value="0">
                                    <label for="boot">Boots</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="crossbow" type="number" min="0" value="0">
                                    <label for="crossbow">Crossbows</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="sword" type="number" min="0" value="0">
                                    <label for="sword">Swords</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="Tea" type="number" min="0" value="0">
                                    <label for="Tea">Tea</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="coin" type="number" min="0" value="0">
                                    <label for="coin">Coins</label>
                                </div>
                                <div class="input-field col s4 m3">
                                    <input id="hammer" type="number" min="0" value="0">
                                    <label for="hammer">Hammers</label>
                                </div>
                            </div>
                        </form>
                        <h5><a name="buildings"></a>Buildings</h5>
                        <table class="responsive-table">
                            <tr>
                                <th>Fox</th>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+1</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+2</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+3</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+4</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+5</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/sawmill.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+6</div>
                                        </div>
                                    </div>
                            </tr>

                            <tr>
                                <th>Bunny</th>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+1</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+2</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+3</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+4</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+5</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/workshop.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+6</div>
                                        </div>
                                    </div>
                            </tr>
                            <tr>
                                <th>Mouse</th>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+1</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+2</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+3</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+4</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+5</div>
                                        </div>
                                    </div>
                                <td>
                                    <div class="f1_container">
                                        <div class="shadow f1_card">
                                            <div class="front face">
                                                <img src="images/barracks.png" style="height: 45px; width: 45px;" />
                                            </div>
                                            <div class="back face center">+6</div>
                                        </div>
                                    </div>
                            </tr>
                            
                        </table>
                    </div>
                </div>
            </div>

            <ul class="collapsible collection with-header">
                    <li class="collection-header"><h5><a name="turn"></a>Turn Order</h5></li>
                <li class="active">
                    <div class="collapsible-header"> 
                        <h6>Birdsong</h6>
                    </div>
                    <div class="collapsible-body"> 
                        <ol>
                            <li><b>Reveal</b> the top card of the deck as order card.</li>
                            <li>
                                <b>Craft</b> order card for +1 if it shows an available item.
                            </li>
                        </ol>
                    </div>
                </li>
                <li class="active">
                    <div class="collapsible-header"> 
                        <h6>Daylight</h6>
                    </div>
                    <div class="collapsible-body"> 
                        <ol>
                            <li>
                                <b>Battle</b> in clearings matching order card.
                            </li>
                            <li><span id="easy"><b>Recruit</b> 3 warriors evenly spread across clearings you rule matching order card. <small>Defender is the player with most pieces, then victory points, then highest priority setup.</small> <br> Bird suit: Instead recruit 2 warriors in the clearing you rule with lowest priority and 1 warrior in the clearing with the 2<sup>nd</sup> lowest priority.</span>
                                <span id="easy"><b>Recruit</b> 4 warriors evenly spread across clearings you rule matching order card. <small>Defender is the player with most pieces, then victory points, then highest priority setup.</small> <br> Bird suit: Instead recruit 2 warriors in each of the 2 clearings you rule with lowest priority.</span>
                                <span id="normal"><b>Recruit</b> 5 warriors evenly spread across clearings you rule matching order card. <small>Defender is the player with most pieces, then victory points, then highest priority setup.</small> <br> Bird suit: Instead recruit 3 warriors in the clearing you rule with lowest priority and 2 warriors in the clearing with the the 2<sup>nd</sup> lowest priority.</span>
                                <span id="hard"><b>Recruit</b> 5 warriors evenly spread across clearings you rule matching order card. <small>Defender is the player with most pieces, then victory points, then highest priority setup.</small> <br> Bird suit: Instead recruit 2 warriors in the clearing you rule with lowest priority and 3 warrior in the clearing with the 2<sup>nd</sup> lowest priority.</span>
                                <br> Gain +1 for every 2 warriors that could not be recruited.
                            </li>
                            <li>
                                <b>Build</b> 1 building matching order card in a clearing you rule. <br>
                                Bird suit: Place building type with most pieces already on the board. <small>If tied, prioritize in this order: Fox, Bunny, Mouse. Clearing with most of your warriors first, then clearing priority.</small>
                            </li>
                            <li>
                                <b>Move</b> all but 3 of your warriors from clearings matching order card. <br>
                                Bird suit: After completing all moves, battle in all destination clearings. <small>Destination is adjacent clearing with most enemies pieces first, then highest clearing priority.</small>
                                <br><span id="blitz">Select the highest priority clearing you rule without any enemy pieces. Move all but 1 warrior from the clearing and battle in the destination if opponents are present.</span>
                            </li>
                            <li>
                                <b>Escalate</b> ff no building was placed due to no available slot on the board and there are less than 4 buildings of that typo on the board. Reveal a new order card and repeat Daylight (once per turn).
                                <br><span id="ironwill"> Escalate may be triggered twice per turn.</span>
                            </li>
                        </ol>
                    </div>
                </li>
                <li class="active">
                    <div class="collapsible-header"> 
                        <h6>Evening</h6>
                    </div>
                    <div class="collapsible-body">
                        <p><b>Score</b> + 1 for each building on the board matching the current order card (bird scores single most). Then discard order card(s). <span id="hardExtra"><br> Score +1 per player.</span></p>
                    </div>
                </li>
            </ul>
        </div>

        <div class="fixed-action-btn">
            <a class="btn-floating btn-large red" onclick="reload()">
                <i class="large material-icons">replay</i>
            </a>
        </div>

    <!--JavaScript at end of body for optimized loading-->
    <script src="https://code.jquery.com/jquery-3.4.1.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/materialize/1.0.0/js/materialize.min.js"></script>
    <script>
        $(document).ready(function(){
            $('#hardExtra').hide();
            $('.tabs').tabs();
            $('.tabs').click(function(){
                if($('#hardTab').hasClass('active')){
                    $('#hardExtra').show();
                } else{
                    $('#hardExtra').hide();
                }
            });

            $('.filled-in').change(function() {
                if($(this).is(":checked")) {
                    var t = $(this).val();
                    if($('#' + t).is(":visible")){
                        $('#' + t).hide();
                    } else {
                        $('#' + t).show();
                    }
                }
            });
            $("#blitz").hide();
            $("#ironwill").hide();
            $("#hospitals").hide();
            $("#fortified").hide();

            $('.collapsible').collapsible({
                accordion: false
            });
            $('.f1_container').click(function() {
                $(this).toggleClass('active');
            });
            $('.fixed-action-btn').floatingActionButton();
            $('.sidenav').sidenav();
        });

        function reload(){
            if(confirm("Reload page?")){
                location.href = "./mm.html";
            }
        }
    </script>
  </body>
</html>