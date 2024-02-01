% Need to stablish the restriction of the balance between missionaries and cannibals
% This function confirms this balance, missionaries on either side of the river
% must be more or equal to the cannibals. 
restriction(CL, ML, CR, MR) :-
    % We state that the number of subjects are all positive, 
    % so the computer does move 2 people in the case only one is available.
    ML >= 0, CL >= 0, MR >= 0, CR >= 0,
    % This compares if the missionaries on the left side are greater of equal to the 
    % cannibals, so they aren’t outnumbered, or the case it also checks if there is none of 
    % them in the left side,so it is safe to move the cannibals in any capacity.
    (ML >= CL ; ML = 0),
    % This is the same comparison but for the right side of the river, it checks the quantity
    % of missionaries on the right to the number of cannibals, or if there 
    % are no missionaries left.
    (MR >= CR ; MR = 0).

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Give the machine the available option for moving the missionaries and the cannibals 
% for each side of the river. 
% 
% All "make_move" fuctions work in a similar manner, we give this function the quantity of 
% missionaries and cannibals on each side and from what side of the river we are stating
% and it will return the new quantities after the move, and the new position of the boat.
%
% There are 5 moves available for each side, 10 in total.

% Move two missionaries from left to right. 
make_move([CL,ML,from_left,CR,MR],[CL,ML2,from_right,CR,MR2]):-
    % As the right-side gains two missionaries, we need to add this quantity 
    % to the variable of missionaries on the right.
    MR2 is MR + 2,
    % As we move two missionaries from left to right, we need to modify our starting 
    % variable of missionaries on the left and subtract the two we just moved.
    ML2 is ML - 2,
    % The restriction verifies the validity of the resulting move as it ensures that the
    % counts of missionaries and cannibals on both banks satisfy the constraints.
    restriction(CL, ML2, CR, MR2).

% Move two cannibals from left to right. 
make_move([CL,ML,from_left,CR,MR],[CL2,ML,from_right,CR2,MR]):-
	% As the right-side gains two cannibals, we need to add this quantity 
    % to the variable of cannibals on the right.
    CR2 is CR + 2,
    % As we move two cannibals from left to right, we need to modify our starting 
    % variable of cannibals on the left and subtract the two we just moved.
    CL2 is CL - 2,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML, CR2, MR).

% Move one missionary and one cannibal  from left to right.
make_move([CL,ML,from_left,CR,MR],[CL2,ML2,from_right,CR2,MR2]):-
    % The cannibals on the right gain one, so we add it to the variable.
    CR2 is CR + 1,
    % The cannibals on the left lose one, so we subtract it from the variable.
    CL2 is CL - 1,
    % The missionaries on the right gain one, so we add it to the variable.
    MR2 is MR + 1,
    % The missionaries on the left lose one, so we subtract it from the variable.
    ML2 is ML - 1,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML2, CR2, MR2).

% Move one missionary from left to right.
make_move([CL,ML,from_left,CR,MR],[CL,ML2,from_right,CR,MR2]):-
    % The missionaries on the right gain one, so we add it to the variable.
    MR2 is MR + 1,
	% The missionaries on the left lose one, so we subtract it from the variable.
    ML2 is ML - 1,
    % The restriction verifies the validity of the move.
    restriction(CL, ML2, CR, MR2).

% Move one cannibal from left to right.
make_move([CL,ML,from_left,CR,MR],[CL2,ML,from_right,CR2,MR]):-
    % The cannibals on the right gain one, so we add it to the variable.
    CR2 is CR + 1,
	% The cannibals on the left lose one, so we subtract it from the variable.
    CL2 is CL - 1,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML, CR2, MR).

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Move two missionaries from right to left.
make_move([CL,ML,from_right,CR,MR],[CL,ML2,from_left,CR,MR2]):-
    % As we move two missionaries from right to left, we need to modify our starting 
    % variable of missionaries on the right and subtract the two we just moved.
    MR2 is MR - 2,
    % As the left side gains two missionaries, we need to add this quantity 
    % to the variable of missionaries on the left.
    ML2 is ML + 2,
    % The restriction verifies the validity of the move.
    restriction(CL, ML2, CR, MR2).

% Move two cannibals from right to left.
make_move([CL,ML,from_right,CR,MR],[CL2,ML,from_left,CR2,MR]):-
    % As we move two cannibals from right to left, we need to modify our starting 
    % variable of cannibals on the right and subtract the two we just moved.
    CR2 is CR - 2,
    % As the left side gains two cannibals, we need to add this quantity 
    % to the variable of cannibals on the left.
    CL2 is CL + 2,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML, CR2, MR).

% Move one missionary and one cannibal from right to left.
make_move([CL,ML,from_right,CR,MR],[CL2,ML2,from_left,CR2,MR2]):-
    % The cannibals on the left lose one, so we substract it from the variable.
    CR2 is CR - 1,
    % The cannibals on the left gain one, so we add it to the variable.
    CL2 is CL + 1,
    % The missionaries on the left lose one, so we substract it from the variable.
    MR2 is MR - 1,
    % The missionaries on the left gain one, so we add it to the variable.
    ML2 is ML + 1,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML2, CR2, MR2).

% Move one missionary from right to left.
make_move([CL,ML,from_right,CR,MR],[CL,ML2,from_left,CR,MR2]):-
    % The missionaries on the left lose one, so we substract it from the variable.
    MR2 is MR - 1,
    % The missionaries on the left gain one, so we add it to the variable.
    ML2 is ML + 1,
	% The restriction verifies the validity of the move.
    restriction(CL, ML2, CR, MR2).

% Move one cannibal from right to left.
make_move([CL,ML,from_right,CR,MR],[CL2,ML,from_left,CR2,MR]):-
    % The cannibals on the left lose one, so we substract it from the variable.
    CR2 is CR - 1,
    % The cannibals on the left gain one, so we add it to the variable.
    CL2 is CL + 1,
    % The restriction verifies the validity of the move.
    restriction(CL2, ML, CR2, MR).


%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Recursive call

% This recursive function is trying to find the best moves to change our initial quantity 
% of missionaries and cannibals from the left side of the river “[CL1,ML1,B1,CR1,MR1]” to 
% our goal of  bringing them to the right “[CL2,ML2,B2,CR2,MR2]”. It requires the list of 
% path we already explored and a list that accumulates the sequence of moves made during 
% the recursion.

find_path([CL1,ML1,B1,CR1,MR1],[CL2,ML2,B2,CR2,MR2],KnownPaths,MovesList) :- 
    % We call the fuction to move from our initial positions to the next one.
    make_move([CL1,ML1,B1,CR1,MR1],[CL3,ML3,B3,CR3,MR3]), 
    % We avoid falling ibto a loop by checking if this new state "[CL3,ML3,B3,CR3,MR3]" has 
    % already been explored, as known paths are stored in the list of KnowPaths. 
    % If it is a new path we move to the recursion to make a new move
    not(member([CL3,ML3,B3,CR3,MR3],KnownPaths)),
    % this recursion starts with this new distribution of cannibals and missionaries, and 
    % tries to reach our goal, it stores this move into KnowPaths and records the valid 
    % move into the MovesList (note we are storing them with the new position first).
    find_path([CL3,ML3,B3,CR3,MR3],[CL2,ML2,B2,CR2,MR2],[[CL3,ML3,B3,CR3,MR3]|KnownPaths],
              [ [[CL3,ML3,B3,CR3,MR3],[CL1,ML1,B1,CR1,MR1]] | MovesList ]).

% This is the base case for the recursive function, it states when does the recursion ends. 
% In this case is when the position in which we are currently is the same as our final goal, 
% and we end up with the list of moves we made to reaach it.

find_path([CL,ML,B,CR,MR],[CL,ML,B,CR,MR],_,MovesList):- 
    % This function is the one printing the moves we made.
    output_moves(MovesList).

% This is the base case of this recursion, it states that we end it when our list is empty.
output_moves([]) :- nl. 
% This function represents the recursive case. It matches a list of pairs [[A,B]|MovesList], 
% where A is the current position of the missionaries and cannibals, where B is the previous position
% and MovesList is the remaining list.
output_moves([[A,B]|MovesList]) :- 
    % This part makes a recursive call with the remaining list of moves
    output_moves(MovesList), 
    % the part of the function that actually prints the final answer, note that it is in "reverse" 
    % as the way the list stores the valid moves is the last move first and the initial position last.
    write(B), write(' -> '), write(A), nl.

%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%

% Function that calls our recursive methods to find a path.
find_solution :- 
    % We input the position of our missionaries and cannibals and the way the boat will move 
    % first as well as the position we want to reach, in this case all of them crossing the river, 
    % additionally we add this current position to the KnowPaths list and start our Moveslist.
    
    find_path([3,3,from_left,0,0],[0,0,from_right,3,3],[[3,3,from_left,0,0]],_).


