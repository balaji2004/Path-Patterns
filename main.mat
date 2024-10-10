% Load the sensor data
load('clutch.mat')

% Function to calculate elapsed time in seconds
function newArray = timeElapsed(datetime_array)
    if isempty(datetime_array)
        error('Input datetime array is empty.');
    end

    % Convert datetime array to seconds
    newArray = second(datetime_array);
    arraySize = numel(newArray); % Number of elements in the array
    first = newArray(1);
    i = 1;

    % The following loop will run until it reaches the end of the array.
    while i < arraySize
        if newArray(i) > newArray(i+1)
            newArray(i+1) = newArray(i+1) + 60;
            i = 1;
        end
        i = i + 1;
    end

    % Subtract the first number from all elements to start the array at 0.
    newArray = newArray - first;
end

% Extract the row times (timestamps) from Position data and convert to elapsed time
if istimetable(Position)
    positionTime = Position.Properties.RowTimes;
    positionTime = timeElapsed(positionTime);
else
    error('Position is not a timetable.');
end

%% Initialize Variables

earthCirc = 24901 * 5280;  % 24901 miles, convert to feet
totaldis = 0; 
stride = 2.5;  % feet (average stride length)
lat = Position.latitude;  % Access latitude from the timetable
lon = Position.longitude;  % Access longitude from the timetable

%% Processing Loop

for i = 1:(length(lat) - 1)  % Loop through every data sample
    lat1 = lat(i);  % Latitude of the i'th sample
    lon1 = lon(i);  % Longitude of the i'th sample
    lat2 = lat(i + 1);  % Latitude of the (i+1)'th sample
    lon2 = lon(i + 1);  % Longitude of the (i+1)'th sample
    diff = distance(lat1, lon1, lat2, lon2);  % MATLAB function to compute 
                                               % distance between 2 points
    dis = (diff / 360) * earthCirc;  % Convert degrees to feet
    totaldis = totaldis + dis;
end

% Calculate the number of steps
steps = totaldis / stride;

% Plot the latitude and longitude route
figure;
plot(lat, lon, '-r', lat(1), lon(1), '*g', lat(end), lon(end), '*b', 'LineWidth', 3, 'MarkerSize', 10);
hold on;
legend('Route', 'Start Point', 'End Point');
xlabel('Latitude');
ylabel('Longitude');
title(sprintf('Workout Summary: You took %.0f steps and moved %.3f miles', steps, totaldis / 5280));
hold off;

% Load the sensor data
load('clutch.mat')

% Function to calculate elapsed time in seconds
function newArray = timeElapsed(datetime_array)
    if isempty(datetime_array)
        error('Input datetime array is empty.');
    end

    % Convert datetime array to seconds
    newArray = second(datetime_array);
    arraySize = numel(newArray); % Number of elements in the array
    first = newArray(1);
    i = 1;

    % The following loop will run until it reaches the end of the array.
    while i < arraySize
        if newArray(i) > newArray(i+1)
            newArray(i+1) = newArray(i+1) + 60;
            i = 1;
        end
        i = i + 1;
    end

    % Subtract the first number from all elements to start the array at 0.
    newArray = newArray - first;
end

% Extract the row times (timestamps) from Position data and convert to elapsed time
if istimetable(Position)
    positionTime = Position.Properties.RowTimes;
    positionTime = timeElapsed(positionTime);
else
    error('Position is not a timetable.');
end

%% Initialize Variables

earthCirc = 24901 * 5280;  % 24901 miles, convert to feet
totaldis = 0; 
stride = 2.5;  % feet (average stride length)
lat = Position.latitude;  % Access latitude from the timetable
lon = Position.longitude;  % Access longitude from the timetable

%% Processing Loop

for i = 1:(length(lat) - 1)  % Loop through every data sample
    lat1 = lat(i);  % Latitude of the i'th sample
    lon1 = lon(i);  % Longitude of the i'th sample
    lat2 = lat(i + 1);  % Latitude of the (i+1)'th sample
    lon2 = lon(i + 1);  % Longitude of the (i+1)'th sample
    diff = distance(lat1, lon1, lat2, lon2);  % MATLAB function to compute 
                                               % distance between 2 points
    dis = (diff / 360) * earthCirc;  % Convert degrees to feet
    totaldis = totaldis + dis;
end

% Calculate the number of steps
steps = totaldis / stride;

% Plot the latitude and longitude route
figure;
plot(lat, lon, '-r', lat(1), lon(1), '*g', lat(end), lon(end), '*b', 'LineWidth', 3, 'MarkerSize', 10);
hold on;
legend('Route', 'Start Point', 'End Point');
xlabel('Latitude');
ylabel('Longitude');
title(sprintf('Workout Summary: You took %.0f steps and moved %.3f miles', steps, totaldis / 5280));
hold off;