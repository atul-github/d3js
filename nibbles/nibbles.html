<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <title>Simple Snake game in D3js</title>
    <script src="http://d3js.org/d3.v3.min.js"></script>
</head>
<body>

<script>
    // nibble object - multiple snakes can be created by instantiating new objects
    function Nibble(svg, x, y, id, color) {
        this.startX = x;
        this.startY = y;
        this.color = color;
        this.width = 12;
        this.height = 12;
        this.svg = svg;
        this.id = id;
        this.headBoxId = 1;
        this.tailBoxId = 1;
        this.skipCount = 0;
        this.direction = 'right';
        this.prizeLocation = null;
        var thisobj = this;

        this.SetPrizeLocation = function (pt) {
            this.prizeLocation = pt;
        }

        this.Draw = function () {
            svg.append("rect")
                .attr("id", thisobj.id + "_" + thisobj.headBoxId)
                .attr("x", thisobj.startX)
                .attr("y", thisobj.startY)
                .attr("height", thisobj.height)
                .attr("width", thisobj.width)
                .style("fill", function () {
                    if (typeof (thisobj.color) == 'undefined')
                        return "red";
                    else
                        return thisobj.color;
                })
                .style("stroke", function() {
                    if (typeof (thisobj.color) == 'undefined')
                        return "red";
                    else
                        return thisobj.color;
                })
                ;
            }

            this.SetSkip = function (skip) {
                thisobj.skipCount = skip;
            }

            this.SetDirection = function (direction) {
                thisobj.direction = direction;
            }

            this.Move = function () {
                var direction = thisobj.direction;
                thisobj.headBoxId++;

                if (direction.toLowerCase() == 'right') {
                    thisobj.startX += thisobj.width;
                    if (parseInt(svg.attr('width')) <= thisobj.startX) {
                        thisobj.startX = 0;
                    }
                }
                else if (direction.toLowerCase() == 'left') {
                    thisobj.startX -= thisobj.width;
                    if (thisobj.startX < 0) {
                        thisobj.startX = parseInt(svg.attr('width')) - thisobj.width;
                    }
                }
                else if (direction.toLowerCase() == 'down') {
                    thisobj.startY += thisobj.height;
                    if (parseInt(svg.attr('height')) <= thisobj.startY) {
                        thisobj.startY = 0;
                    }
                }
                else if (direction.toLowerCase() == 'up') {
                    thisobj.startY -= thisobj.height;
                    if (thisobj.startY < 0) {
                        thisobj.startY = parseInt(svg.attr('height')) - thisobj.height;
                    }
                }

                thisobj.Draw();

                if (thisobj.skipCount > 0) {
                    thisobj.skipCount--;
                }
                else {
                    thisobj.svg.select('#' + thisobj.id + "_" + thisobj.tailBoxId).remove();
                    thisobj.tailBoxId++;
                }

                if (thisobj.prizeLocation != null
                   && (
                       ( thisobj.startY >= thisobj.prizeLocation.y
                       && thisobj.startY <= (thisobj.prizeLocation.y + thisobj.height)
                       && thisobj.startX >= thisobj.prizeLocation.x
                       && thisobj.startX <= (thisobj.prizeLocation.x + thisobj.width) )
                       ||
                       (thisobj.prizeLocation.y >= thisobj.startY
                       && thisobj.prizeLocation.y <= (thisobj.startY + thisobj.height)
                       && thisobj.prizeLocation.x >= thisobj.startX
                       && thisobj.prizeLocation.x <= (thisobj.startX + thisobj.width))
                       )
                    )
                    return 'IATE';
            }
        }

        function Prize(svg) {
            this.posX = 100;
            this.posY = 100;
            this.color = 'green';
            this.width = 12;
            this.height = 12;
            this.svg = svg;
            this.id = 'imprize';
            var thisObj = this;

            this.Draw = function () {

                svg.select('#' + thisObj.id).remove();

                svg.append("rect")
                .attr("id", thisObj.id)
                .attr("x", thisObj.posX)
                .attr("y", thisObj.posY)
                .attr("height", thisObj.height)
                .attr("width", thisObj.width)
                .style("fill", function () {
                    if (typeof (thisObj.color) == 'undefined')
                        return "red";
                    else
                        return thisObj.color;
                })
                .style("stroke", function () {
                    if (typeof (thisObj.color) == 'undefined')
                        return "red";
                    else
                        return thisObj.color;
                })
                ;
            }

            this.SetNewLocation = function (maxX, maxY) {
            }

            this.GetPrizeLocation = function () {
                return { x: thisObj.posX, y: thisObj.posY };
            }
        }

        var nibbles = [];
        var prize;

    function Initialize(containerId) {
        var height = document.getElementById(containerId).clientHeight;
        var width = document.getElementById(containerId).clientWidth;
        gContainerId = containerId;
        gCanvasId = containerId + '_canvas';
        gTopGroupId = containerId + '_topGroup';
        var svg = d3.select("#" + containerId).append("svg")
            .attr("id", gCanvasId)
            .attr("width", width)
            .attr("height", height)
            .append("g")
            .attr("id", gTopGroupId)
            .attr("x", 0)
            .attr("y", 0)
            .attr("width", width)
            .attr("height", height)
            .style("fill", "none")
            //.attr("transform", "translate(" + 1 + "," + 1 + ")")
            ;

        nibbles.push(new Nibble(svg, 10, 10, 'n1', 'red'));
        //nibbles.push(new Nibble(svg, 10, 10, 'n2', 'yellow'));

        prize = new Prize(svg);
        prize.Draw();

        for (var i = 0; i < nibbles.length; ++i) {
            nibbles[i].Draw();
            nibbles[i].SetPrizeLocation(prize.GetPrizeLocation());
        }

        d3.select('body')
            .on('keydown', function () {
                if (nibbles.length == 0)
                    return;
                if (d3.event.keyIdentifier == 'Down'
                    || d3.event.keyIdentifier == 'Up'
                    || d3.event.keyIdentifier == 'Right'
                    || d3.event.keyIdentifier == 'Left'
                ) {
                    d3.event.preventDefault();
                }

                if (d3.event.keyIdentifier == 'Down')
                    nibbles[0].SetDirection('down');
                else if (d3.event.keyIdentifier == 'Up')
                    nibbles[0].SetDirection('up');
                else if (d3.event.keyIdentifier == 'Right')
                    nibbles[0].SetDirection('right');
                else if (d3.event.keyIdentifier == 'Left')
                    nibbles[0].SetDirection('left');
                else if (d3.event.keyCode == 27) {
                    StartStopGame();
                }
                //console.log(d3.event);
            });

        return svg;

    }

    var intervalId=null;
    function StartStopGame() {
        if (intervalId == null) {
            document.getElementById('startStop').innerHTML = 'Stop';
            intervalId = setInterval(function () {
                for (var i = 0; i < nibbles.length; ++i) {
                    var r = nibbles[i].Move();
                    if (r == 'IATE') {
                        nibbles[i].SetSkip(5);
                    }
                }
            }, 100);
        }
        else {
            clearInterval(intervalId);
            intervalId = null;
            document.getElementById('startStop').innerHTML = 'Start';
        }
    }

</script>

<div id="mainDiv" style="width:800px; height:500px">
    <div id="drawAreaOuter" style="width:100%; height:100%; float:left; ">
        <div id="menuTop" >
            <a id="startStop" href="javascript:StartStopGame()" >Start</a>
        </div>
        <div id="drawArea" style="width:100%; height:100%; border:1px solid gray">
        </div>
    </div>
</div>

<script>
    var svg = Initialize('drawArea');
</script>

</body>
</html>
